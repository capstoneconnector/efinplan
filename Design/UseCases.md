
# Actors

* Investors
	* Investors are those who use eFinPlan to receive financial advice. 
* Advisors
	* Advisors are those who use eFinPlan  to educate Investors about managing finances.
* MX
	* MX is an external platform that aggregates financial information from an individual's bank.
* AMember
	* AMember is an external subscription-based billing service.
* MoneyTree Plan
	* MoneyTree Plan is a service that provides calculators for financial planning.

# Use Cases

* UC1: Publish financial education content
	* Description: This use case is needed because the platform is meant to teach Investors about financial topics. In order to do this, eFinPlan will host a catalogue of curated financial education content. These resources must be found or made and then published onto the site. Therefore, eFinPlan needs to be used to publish content.
	* Actors: Advisors
	* Flow: First, the Advisor will either make or find content that they would like to be available on the platform. Then, they will click a button to publish the content. They will fill out information about the content and finally click a publish button.
	* Business Requirement: BR1

* UC2: View financial education content
	* Description: This use case is needed because the platform is meant to provide financial education resources to Investors. After content is published by Advisors, it needs to be viewable by Investors looking to learn or Advisors in need of reference. Therefore, eFinPlan needs to have viewable financial education content.
	* Actors: Investors, Advisors
	* Flow: After an Advisor has published content to eFinPlan, Investors or Advisors can view all available content and select one to view in full.
	* Business Requirement: BR1
 
 * UC3: Tag financial education content
	* Description: This use case is needed because financial education resources published to the site need to be organized for Investors to find what they need. Tags can be used to differentiate content based on what they contain. Therefore, eFinPlan can differentiate and organize content based on tags added to published content.
	* Actors: Advisors
	* Flow: As an Advisor publishes content, they are able to add tags using an input field to the content they are publishing.
	* Business Requirement: BR4

 * UC4: Search financial education content
	* Description: This use case is needed because Investors need to find content based around their needs. By including a search feature to the site, Investors can search the title and tags of content to find what they need to know instead of only being able to browse all available content. Therefore, eFinPlan needs a search feature so that Investors can limit what they see based around their needs. 
	* Actors: Investors, Advisors
	* Flow: After content has been published, Investors and Advisors can type in a search bar to filter content that matches their search in either name or tag. Once filtered, they can see the content that matches their search and click on one to view.
	* Business Requirement: BR4

 * UC5: Schedule financial advising appointment
	* Description: This use case is needed because eFinPlan is meant to offer Investors financial advice directly from Advisors. Scheduling appointments allows for Investors and Advisors to meet so that Investors can receive direct advice. Therefore, eFinPlan needs a system for Investors to schedule an appointment with Advisors.
	* Actors: Investors
	* Flow: Investors can view a selection of available appointments with their Advisor for the month. From there, they can click on one to fill out information and schedule it.
	* Business Requirement: BR2

 * UC6: View scheduled financial advising appointments
	* Description: This use case is needed because Investors and Advisors need to be able to view all of their scheduled meetings and their statuses. In order for Advisors to view their schedule of appointments, they need to be able to see all scheduled appointments and the statuses of the appointments. Similarly, Investors need to see the statuses of appointments they have scheduled. Hence, eFinPlan needs to display all scheduled financial advising appointments to the Investors and Advisors involved.
	* Actors: Investors, Advisors
	* Flow: After an appointment has been scheduled, both the Investor and Advisor involved shall be able to view all of their scheduled appointments. By clicking on one, they can view the appointment information.
	* Business Requirement: BR2

 * UC7: Mark scheduled financial advising appointment attendance
	* Description: This use case is needed because Investors and Advisors may need to change the status of a scheduled appointment to accepted or declined based on their availability. For example, if unforeseen circumstances make it such that an Advisor cannot attend an appointment, they can mark that appointment as declined so that the Investor can reschedule. Therefore, eFinPlan must allow Investors and Advisors to mark the attendance of their scheduled appointments.
	* Actors: Investors, Advisors
	* Flow: After clicking on an appointment to view the details, the Advisor involved can click a button to choose to accept or decline the meeting. An Investor may choose to cancel the meeting.
	* Business Requirement: BR2

 * UC8: Form financial plan
	* Description: In order for eFinPlan to accomplish its goal of helping Investors in financial education, the platform should offer an area for Investors to plan out their financial goals. Investors should be able to make a plan based on goals such as how much money they wish to have when they retire. These goals can later be seen by their financial Advisor so that the Advisor can better tailor content and advice for the Investor. Hence, eFinPlan needs a space for Investors to plan out their financial goals.
	* Actors: Investors
	* Flow: After clicking a button to create a new financial plan or edit an existing one, Investors fill out the information of the plan, such as how much money they want to have after a certain age, and then submit the plan. 
	* Business Requirement: BR3

 * UC9: View financial plan
	* Description: This use case is needed so that Advisors can see the financial plans of the Investors that they advise. This is so that they can help the Investors achieve their goal using content on the site or by giving direct advice during appointments. Investors also need to review their own financial plans to ensure they are on track. Therefore, eFinPlan must allow an Investor and their Advisor to view the Investor's financial plan. 
	* Actors: Investors, Advisors
	* Flow: Once a financial plan has been created, an Investor or their Advisor can click a button to view the financial plan for that Investor. 
	* Business Requirement: BR3

 * UC10: Use MoneyTree calculators
	* Description: MoneyTree has various existing calculators for topics related to finances, such as retirement. In order to leverage these existing tools, eFinPlan can use MoneyTree's calculators on the site. Therefore, in order to enhance the experience of Investors using the site to educate themselves about finances, eFinPlan should allow Investors to use these existing MoneyTree calculators when forming their financial plans.
	* Actors: Investors, MoneyTree Plan
	* Flow: While viewing their financial plan, Investors are able to click on any of the available MoneyTree calculators to use them. The responses of the calculators may be used to assist in editing or creating a financial plan.
	* Business Requirement: BR6

 * UC11: Subscribe to eFinPlan
	* Description: This use case is needed so that eFinPlan can monetize the service. MoneyTree, which owns eFinPlan, is partnered with AMember, so the platform must use AMember in order to lock parts of the site under a paywall. In order for Advisors to use the site, they must pay the subscription to eFinPlan before they register. Therefore, eFinPlan must allow for Advisors to subscribe using AMember prior to registration.
	* Actors: Advisors, AMember
	* Flow: Once an Advisor can register for the site, they are prompted with a button to go to AMember to purchase the subscription to eFinPlan. Once the subscription goes through, they are allowed to complete registration.
	* Business Requirement: BR5

 * UC12: Connect bank information to eFinPlan
	* Description: In order to offer a single place for Investors to quickly view all of their financial information, MoneyTree has partnered with MX, a platform that aggregates financial information from banks. MX allows the Investor to log in with their bank, which sends all of the financial information from the bank to eFinPlan. Therefore, to quickly aggregate Investors' financial information, eFinPlan will allow Investors to connect their bank information using MX.
	* Actors: Investors, MX
	* Flow: Once an Investor registers their account, they will be prompted to click a button that brings them to MX. At the MX page, they can fill out their bank information.
	* Business Requirement: BR7

 * UC13: View aggregated financial information
	* Description: Because MoneyTree wants to aggregate financial information for Investors so that they can get help in creating financial plans, eFinPlan will use the information received from MX to display all of the Investor's relevant data in one area. This will allow the Investor to view all of their relevant bank information in one place so that they can reference it when creating their financial plans. Also, Advisors may be able to use some of the data in order to better advise Investors. Therefore, eFinPlan should display the aggregated information from MX.
	* Actors: Investors, MX
	* Flow: After an Investor connects their bank information using MX, they can view all of the received information on one page.
	* Business Requirement: BR7
