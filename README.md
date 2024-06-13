## Cybet Test System
 This is build in python flask framework, its developed to help in understanding of cyber security concepts such as Cross SIte Scripting, Broken Access Control, Session Managements

 ## Set Up

 ### Installation

    pip3 install pymysql 

 Install Xampp and import the database named CyberTestSystem.sql. 
 Open VS Code and open the Folder containing the python project.

 Run your Flask App.
 Access  http://127.0.0.1:5000/signin

 ### Broken Access Control 
 The Application has 2 user Account: Admin and User Roles<br>
 Admins can only View Messages and Users can Only Add a Message. <br>

 Login Credentials


  ![Alt text](db.png)


 The Application demonstrates how to SOlve Broken Access Control Issues in Cyber Security by having different users have access to specific functions in the System. 


 ### Broken Access Control Protection
 Broken Access Control is a significant security vulnerability where users can access data or functions they are not entitled to. To secure against broken access control, consider implementing the following best practices:

 <br>
 1. Enforce Least Privilege<br>
Minimal Access: Ensure users have the least privilege necessary to perform their functions. Regularly review roles and permissions to adjust as needed.<br>
Role-Based Access Control (RBAC): Implement RBAC to manage user permissions. Assign roles based on job functions and ensure these roles have the minimum required permissions.<br>

2. Use Strong Access Controls<br>
Authentication: Use strong, multi-factor authentication (MFA) to verify user identities.
Session Management: Properly manage user sessions, ensuring they time out after a period of inactivity and regenerate session IDs upon login.<br>

3. Implement Access Control Mechanisms<br>
Centralized Access Control Logic: Implement centralized access control logic to avoid inconsistencies. Use a single point of access control for all resource checks.
Deny by Default: Deny access by default, and explicitly grant permissions where necessary.

4. Validate Permissions on Server-Side<br>
Server-Side Checks: Always enforce access control on the server side. Never rely on client-side controls, as they can be bypassed.<br>
Parameterize Access Checks: Use parameterized access checks to ensure permissions are verified against each specific resource or action.<br>

5. Use Secure Development Practices<br>
Code Reviews: Conduct regular code reviews focusing on access control issues.
Security Testing: Perform security testing, including automated scanning and manual penetration testing, to identify and fix access control weaknesses.<br>
Static and Dynamic Analysis: Use static code analysis tools to identify potential access control flaws and dynamic analysis tools to verify the application's behavior.<br>

6. Implement Logging and Monitoring<br>
Audit Logs: Maintain detailed logs of access control decisions and user actions. Monitor these logs for suspicious activity.<br>
Real-Time Monitoring: Implement real-time monitoring and alerting for access control violations.

7. Education and Awareness<br>
Developer Training: Educate developers about access control risks and best practices. Ensure they understand the importance of secure coding practices.
User Awareness: Inform users about the importance of secure practices, such as not sharing credentials and recognizing phishing attempts.<br>

8. Review and Update Access Controls Regularly<br>
Regular Audits: Regularly audit access controls and update them as necessary. Ensure that permissions are still appropriate for current user roles.<br>
Automated Tools: Use automated tools to help manage and review access control configurations.

10. Use Frameworks and Libraries<br>
Security Frameworks: Leverage security frameworks and libraries that provide built-in access control mechanisms, such as Spring Security for Java or ASP.NET Identity for .NET applications.


 ### Stored XSS
 Stored XSS, also known as persistent XSS, is the more damaging of the two. It occurs when a malicious script is injected directly into a vulnerable web application. Reflected XSS involves the reflecting of a malicious script off of a web application, onto a user's browser.

 This application also demonstrates stored XSS scenario and their Protection.



 ### XSS Protection
 o protect against stored XSS, follow these best practices:

1. Input Validation and Sanitization<br>
Whitelist Input Validation: Only allow expected inputs. For example, if a field is expected to contain only numbers, ensure that it contains only numbers.
Sanitize Input: Remove or escape special characters that could be used to inject malicious scripts. Use libraries or built-in functions to sanitize input. For example, in PHP, use htmlspecialchars() to convert special characters to HTML entities.
<br>

2. Output Encoding<br>
HTML Encoding: Encode all user-generated content before outputting it in HTML. This prevents the browser from interpreting it as executable code. For example, in JavaScript, you can use textContent instead of innerHTML.
Attribute Encoding: Properly encode data being placed in HTML attributes. Use functions like htmlspecialchars() or htmlescape() in your server-side language.
JavaScript Encoding: When inserting user data into JavaScript, ensure it's properly encoded to avoid script injection.

<br>
3. Content Security Policy (CSP)<br>
Implement a Content Security Policy to restrict the sources from which your web application can load resources. This can help mitigate the impact of XSS by blocking the execution of malicious scripts.

<br>
Content-Security-Policy: script-src 'self';
<br>
4. HTTPOnly and Secure Cookies<br>
HTTPOnly Cookies: Set the HttpOnly flag on cookies to prevent access to them via JavaScript.
Secure Cookies: Use the Secure flag to ensure cookies are only sent over HTTPS.

<br>
5. Web Application Firewalls (WAFs)<br>
Deploy a web application firewall that can detect and block malicious requests based on patterns.

<br>
6. Regular Security Audits and Penetration Testing<br>
Conduct regular security audits and penetration testing to identify and fix vulnerabilities before they can be exploited.

<br>
7. Frameworks and Libraries<br>
Use modern web frameworks that automatically handle many common security concerns, including XSS protection. For example, frameworks like React and Angular escape data by default.

<br>
8. Proper Session Management<br>
Implement proper session management practices to minimize the risk of session hijacking due to XSS. This includes setting appropriate session timeouts and regenerating session IDs on login.

<br>
9. Educate Developers<br>
Ensure that developers are educated about security best practices and understand the common vectors for XSS attacks and how to prevent them.