# Domain Model

![Domain_Model](https://user-images.githubusercontent.com/70241666/195270397-d115a01c-7e00-4db0-ab06-893d353bc673.png)

# Explanation
* User
  * This is an abstract class that acts as the superclass for both Advisors and Investors. It contains properties that are shared between the both of them, such as an Id, email, etc.
* Advisor
  * This class inherits from User and acts as the class representation of an Advisor who would use the site to publish and edit content, attend appointments with Investors, and tag content that can be found on the site. Although the role of an Advisor would do all of those actions, the functions themselves will be contained in each respective object; hence, there are no extra attributes or functions included on the class in the diagram.
* Investor
  * This class inherits from User and acts as the class representation of an Investor who would use the site to create and edit financial plans, create or cancel appointments with Advisors, and favorite or unfavorite content. As with Advisor, the functions for doing those actions are delegated to each respective class; however, Investors can favorite content, which is something that affects the Investor, not the content.
* Appointment
  * This class represents a scheduled meeting between an Investor and an Advisor. Appointments can be accepted or denied by the Advisor and canceled by the Investor; because these actions only change the appointment, the Appointment class holds these functions.
* Financial Plan
  * This class represents a financial plan as created by an Investor on the site. It contains various information that can then be used on the site to calculate things such as a monthly deposit needed to achieve the goal.
* Content
  * This class represents the content added to the site or published by an Advisor. The content can be tagged by an Advisor; because this action affects only the content tagged, its function is delegated to this Content class.
