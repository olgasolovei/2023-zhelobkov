DECLARE @XMLData XML
SET @XMLData = '<root>
    <Vacancy>
        <vacancy_id>1</vacancy_id>
        <title>Software Developer(Middle)</title>
        <description>Exciting job opportunity for a skilled developer</description>
        <requirements>Досвід з node.js</requirements>
    </Vacancy>
    <AuthorizedUser>
        <user_id>1</user_id>
        <firstname>Микита</firstname>
        <lastname>Желобков</lastname>
        <phonenum>+380956235162</phonenum>
        <email>m.zhelobkov@example.com</email>
        <respondVacancy>1</respondVacancy>
    </AuthorizedUser>
    <Recruiter>
        <recr_id>1</recr_id>
        <name>Марина Шептицька</name>
        <phonenum>+380987654321</phonenum>
    </Recruiter>
    <Question>
        <question_id>1</question_id>
        <author>Желобков</author>
        <text>Коли візьмете?</text>
    </Question>
    <VacancyReview>
        <vacr_id>1</vacr_id>
        <author>Желобков Микита</author>
        <vacancy>1</vacancy>
        <text>Візьміть</text>
    </VacancyReview>
</root>'

-- Insert data into the Vacancy table
INSERT INTO Vacancy (vacancy_id, title, description, requirements)
SELECT
    vacancy.value('(vacancy_id)[1]', 'INT') AS vacancy_id,
    vacancy.value('(title)[1]', 'VARCHAR(255)') AS title,
    vacancy.value('(description)[1]', 'TEXT') AS description,
    vacancy.value('(requirements)[1]', 'TEXT') AS requirements
FROM @XMLData.nodes('/root/Vacancy') AS T(vacancy)

-- Insert data into the AuthorizedUser table
INSERT INTO AuthorizedUser (user_id, firstname, lastname, phonenum, email, respondVacancy)
SELECT
    user.value('(user_id)[1]', 'INT') AS user_id,
    user.value('(firstname)[1]', 'VARCHAR(255)') AS firstname,
    user.value('(lastname)[1]', 'VARCHAR(255)') AS lastname,
    user.value('(phonenum)[1]', 'VARCHAR(20)') AS phonenum,
    user.value('(email)[1]', 'VARCHAR(255)') AS email,
    user.value('(respondVacancy)[1]', 'INT') AS respondVacancy
FROM @XMLData.nodes('/root/AuthorizedUser') AS T(user)
INSERT INTO Recruiter (recr_id, name, phonenum)
SELECT
    recruiter.value('(recr_id)[1]', 'INT') AS recr_id,
    recruiter.value('(name)[1]', 'VARCHAR(255)') AS name,
    recruiter.value('(phonenum)[1]', 'VARCHAR(20)') AS phonenum
FROM @XMLData.nodes('/root/Recruiter') AS T(recruiter)

-- Insert data into the Question table
INSERT INTO Question (question_id, author, text)
SELECT
    question.value('(question_id)[1]', 'INT') AS question_id,
    question.value('(author)[1]', 'VARCHAR(255)') AS author,
    question.value('(text)[1]', 'TEXT') AS text
FROM @XMLData.nodes('/root/Question') AS T(question)

-- Insert data into the VacancyReview table
INSERT INTO VacancyReview (vacr_id, author, vacancy, text)
SELECT
    vacancyReview.value('(vacr_id)[1]', 'INT') AS vacr_id,
    vacancyReview.value('(author)[1]', 'VARCHAR(255)') AS author,
    vacancyReview.value('(vacancy)[1]', 'INT') AS vacancy,
    vacancyReview.value('(text)[1]', 'TEXT') AS text
FROM @XMLData.nodes('/root/VacancyReview') AS T(vacancyReview)
