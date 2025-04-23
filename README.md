XSSposed - TryHackMe Room Write-Up

 Introduction

Warm greetings from XSSposed, a TryHackMe room that teaches participants Cross-Site Scripting (XSS) vulnerabilities with hands-on, real-world simulation exercises. You will learn the three principal types of XSS: Stored, Reflected, and DOM-Based. Each of these will be represented in tasks modeled after real-world scenarios.

The room is a combination of hosted labs and downloadable HTML applications which resemble and function like real websites. Learners are given a taste of the experience that security experts have during bug bounty and penetration testing skirmishes.



Challenge Setup

Lab Types:

Hosted Reflected and Stored XSS Labs: Labs hosted online to simulate vulnerable web features
Downloadable HTML lab for DOM-Based XSS: Simulates client-side vulnerabilities within realistic frontend code



Objectives

1.Understand the differences between each type of XSS and how they function.
2.Learn to identify and exploit XSS in multiple scenarios.
3.Locate concealed flags within exploitable applications.
4.Comprehend ways to mitigate each type of vulnerability mentioned above.



Room Task Breakdown

Task 1: Understanding Cross-Site Scripting (XSS)

Covers the theory behind XSS and introduces its types. Includes beginner-friendly quiz questions.

Task 2: Reflected XSS - Unmask the Vulnerability

Theoretical explanation of how reflected XSS works via URL parameters. Reinforced with short quiz.

Task 3: Reflected XSS - Exploitation

Lab:Hosted web application simulating a search function.

Payload: `<script>alert('XSS')</script>`
Goal: Trigger alert and discover flag reflected in the page.

Task 4: Stored XSS - Theory

Explains how input stored in databases (e.g., blog comments) can be exploited later. Includes quiz.

Task 5: Stored XSS - Exploitation

Lab: Hosted blog system simulating comment storage.

Payload: `<script>alert('XSS')</script>`
Goal: Trigger alert when the page reloads and access the flag stored in the application.
Flag: `THM{XSS_DOM_BASED_EXPLOIT_03}`

Task 6: DOM-Based XSS - Theory & Quiz

Explains client-side vulnerabilities where JavaScript reflects unsanitized input directly into the DOM. Includes concept check.

Task 7: DOM-Based XSS - Exploitation

Lab:Downloadable HTML file designed to simulate a modern, realistic web app.
Behavior: JavaScript reflects user input into the DOM

Payload: `file:///C:/Users/user/Desktop/14-2.html?q=document.getElementById('flag').style.display='block';showCongrats()`

Goal: Modify the page via the URL to execute JavaScript that reveals a hidden DOM element and flag `xss02`



Example Flag Output


THM{XSS_DOM_BASED_EXPLOIT_03}
xss02




Mitigation Tips

1.Sanitize Input:Avoid directly trusting user data
2.Output Encode:Use HTML encoding for content rendered on the page
3.CSP:Set strict Content-Security-Policy headers
4.Modern Frameworks:Use frameworks like React or Angular that auto-handle output escaping




References

[OWASP XSS Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)

[MDN - Cross-Site Scripting (XSS)](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting)



Created By

Gayan Vimukthi Jayasekara
TryHackMe Room: [XSSposed](https://tryhackme.com/jr/XSSposed)






