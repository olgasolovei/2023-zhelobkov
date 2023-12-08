| Об'єкт          | Атрибут          | Короткий опис                    | Тип       | Обмеження                       |
|------------------|------------------|----------------------------------|-----------|---------------------------------|
| Vacancy          | id               | Унікальний ідентифікатор вакансії | Integer   | Унікальні значення              |
| Vacancy          | title            | Заголовок вакансії               | String    | Максимум n символів             |
| Vacancy          | description      | Опис вакансії                   | String    | Максимум n символів             |
| Vacancy          | requirements     | Вимоги до кандидатів             | String    | Максимум n символів             |
| AuthorizedUser   | userid           | Унікальний ідентифікатор користувача | Integer | Унікальні значення            |
| AuthorizedUser   | firstname        | Ім'я користувача                 | String    | Максимум 36 символів             |
| AuthorizedUser   | lastname         | Прізвище користувача              | String    | Максимум 72 символів             |
| AuthorizedUser   | phonenum         | Номер телефону користувача        | String    | Формат: +XXX-XXXX-XXXX          |
| AuthorizedUser   | email            | Адреса електронної пошти користувача | String | Формат: email@example.com      |
| AuthorizedUser   | resume           | Резюме користувача                | String    | Максимум n символів             |
| AuthorizedUser   | respondVacancy   | Відповіді на вакансії            | List      |                                 |
| Recruiter        | recrid           | Унікальний ідентифікатор рекрутера | Integer | Унікальні значення             |
| Recruiter        | name             | Ім'я рекрутера                   | String    | Максимум 36 символів             |
| Recruiter        | phonenum         | Номер телефону рекрутера         | String    | Формат: +XXX-XXXX-XXXX          |
| Recruiter        | vacancyreviews   | Відгуки на вакансії, які рекрутер опрацьовав | List |                            |
| Question         | author           | Автор питання                    | String    | Максимум n символів             |
| Question         | text             | Текст питання                    | String    | Максимум n символів             |
| Question         | id               | Унікальний ідентифікатор питання  | Integer   | Унікальні значення              |
| VacancyReview    | vacrid           | Унікальний ідентифікатор відгуку на вакансію | Integer | Унікальні значення          |
| VacancyReview    | author           | Автор відгуку                   | String    | Максимум n символів             |
| VacancyReview    | vacancy          | Вакансія, на яку залишений відгук | Integer | Унікальний ідентифікатор вакансії |
| VacancyReview    | text             | Текст відгуку                   | String    | Максимум n символів             |
