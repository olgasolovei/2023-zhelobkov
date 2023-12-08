<?xml version="1.0" encoding="UTF-8"?>
<telegramBotInterface>
    <title>Рекрутинг бот</title>
    <description>Цей бот приназначений для пошуку роботи</description>
    <content>
        <button>
            <label>Назад</label>
            <action>Повертає назад до всіх чатів</action>
        </button>
    <messages>
        <message>
            <type>text</type>
            <content>/start</content>
            <sender>user</sender>
            <timestamp>2023-12-08T12:30:00Z</timestamp>
        </message>
        <message>
            <type>text</type>
            <content>Привіт, це рекрутинг бот</content>
            <sender>bot</sender>
            <timestamp>2023-12-08T12:31:00Z</timestamp>
        </message>
    </messages>
        <button>
            <label>Меню</label>
            <action>Розвернути меню боту (Dropdown List)</action>
        </button>
        <button>
            <label>Attachment</label>
            <action>Прикріпити файл</action>
        </button>
        <inputField>
            <label>Message</label>
            <type>text</type>
            <placeholder>Сообщение</placeholder>
        </inputField>
        <button>
            <label>Stickers</label>
            <action>Перейти до вибору стікерів</action>
        </button>
        <button>
            <label>Voice message</label>
            <action>Включити голосвий запис</action>
        </button>
        <button>
            <label>Відправити</label>
            <action>Відправити повідомлення</action>
        </button>
        <button>
            <label>Подивитись вакансії</label>
           <action>Відправити боту команду /getVacancy </action>
        </button>
        <button>
            <label>Подивитись інформацію про компанію</label>
           <action>Відправити боту команду /getInformation </action>
        </button>
        <button>
             <label>Зареєструватись</label>
            <action>Відправити боту команду /registration</action>
        </button>
    </content>
</telegramBotInterface>
