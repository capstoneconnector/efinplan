![Architecture](/Design/Architecture.png)

# Explanation

## Database
* PostgreSQL Database
  * This database is what we use in the project to store user data, such as the data for Investors and Advisors; it is where the backend pulls data to serve to the frontend. It is a module because the database stores the data needed for the backend to send data to the frontend; it can be swapped out with any type of database, we only chose PostgreSQL because the client recommended it.

## .NET Backend
* ContentController
  * ContentController is what sends and receives data about financial education content for the site. It is a module because it is the part of the project that takes and handles data regarding content on the site; no other controller should handle content.
* FinPlanController
  * FinPlanController is what sends and receives data about financial plans made by Investors. It is a module because it is the part of the project that takes and handles data regarding financial plans on the site; no other controller should handle financial plans.
* AppointmentController
  * AppointmentController is what sends and receives data about appointments made by Investors. It is a module because it is the part of the project that takes and handles data regarding appointments on the site; no other controller should handle appointments.
* InvestorController
  * InvestorController is what sends and receives data about Investors. It is a module because it is the part of the project that takes and handles data regarding Investors on the site; no other controller should handle Investors.
* AdvisorController
  * AdvisorController is what sends and receives data about Advisors. It is a module because it is the part of the project that takes and handles data regarding Advisors on the site; no other controller should handle Advisors.
* MoneyTree Plan SDK
  * The MoneyTree Plan SDK is a library that we are making to connect to the existing MoneyTree Plan API, which has tools for financial planning that eFinPlan will feature on the website. It is a module because it is the only part of the backend that interacts with the MoneyTree Plan API, so it can be removed or replaced without affecting the other controllers.
* MoneyTree Plan
  * The MoneyTree Plan API is not something we will be making; rather, it is an API that has tools such as a retirement fund calculator that will be featured on the eFinPlan website. It is a module because it is already self-contained and thus can be integrated with our code as with any API.
* MX
  * MX is a service that aggregates information that it pulls from an individuals bank; in eFinPlan, it is used to gather an Investor's information so that it can be displayed in one spot when they are creating a financial plan. It is a module because it is already self-contained and thus can be integrated with our code, similarly to the MoneyTree Plan API.
* AMember
  * AMember is a service that offers subscription-based billing; it is used to allow Advisors to pay for the license to use eFinPlan. It is a module because it is already self-contained and thus can be integrated with our code easily, similarly to MoneyTree Plan API and MX. 

## Vue Frontend
* ContentPage
  * ContentPage uses ContentController to receive and edit the content to populate on the site and includes the interactive sections that Investors and Advisors will use on the website, using each's respective controller in order to send and receive data. It is a module because it contains all of the user-facing aspects of content; no other part of the frontend will handle content.
* FinPlanPage
  * FinPlanPage uses FinPlanController to receive and edit the information regarding an Investor's financial plan, also using InvestorController to send and receive data regarding the Investor's bank information. It is a module because it contains all of the user-facing aspects of financial plans; no other part of the frontend will handle financial plans.
* AppointmentPage
  * AppointmentPage uses AppointmentController to receive and edit the information regarding appointments, also using InvestorController and AdvisorController to send and receive information regarding the attendees of scheduled appointments. It is a module because it contains all of the user-facing aspects of appointments; no other part of the frontend will handle appointments.
* LoginPage
  * LoginPage uses InvestorController and AdvisorController to send and receive data regarding login information for each type of user. It is a module because no other part of the frontend will handle logging in.
* RegisterPage
  * RegisterPage uses InvestorController and AdvisorController to send and receive data regarding the creation of Investors and Advisors. It is a module because it is the only part of the frontend that will handle registering new users of either type.

## Browser
Because our website will be a locally-hosted web app, there is no hosting layer needed. The browser will directly render the frontend.
