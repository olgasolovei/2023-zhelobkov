CREATE TABLE Vacancy (
    vacancy_id INT PRIMARY KEY,
    title VARCHAR(255),
    description VARCHAR(255),
    requirements VARCHAR(255)
);
CREATE TABLE AuthorizedUser (
    user_id INT PRIMARY KEY,
    firstname VARCHAR(255),
    lastname VARCHAR(255),
    phonenum VARCHAR(20),
    email VARCHAR(255),
    respondVacancy INT,
    FOREIGN KEY (respondVacancy) REFERENCES Vacancy(vacancy_id)
);
CREATE TABLE Recruiter (
    recr_id INT PRIMARY KEY,
    name VARCHAR(255),
    phonenum VARCHAR(20),
    vacancyreviews INT
);
CREATE TABLE Question (
    question_id INT PRIMARY KEY,
    author VARCHAR(255),
    text TEXT
);
CREATE TABLE VacancyReview (
    vacr_id INT PRIMARY KEY,
    author VARCHAR(255),
    vacancy INT,
    text VARCHAR(255),
    FOREIGN KEY (vacancy) REFERENCES Vacancy(vacancy_id)
);
