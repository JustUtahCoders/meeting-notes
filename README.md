# meeting-notes
Notes from group meetings.

## 3/16/2019
Leah and Tucker met at Nostalgia to talk about content/videos/help guides. We determined a good place to start would be a high-level video helping people read and understand their BCI. We wrote a first draft for that video.
We also talked about providing transcripts / "blog post" like articles with each video.

## 3/12/2019
Joel met with Luis, Vicky, and Leonel at Comunidades Unidas for an hour and a half. They gave us access to their AWS and Wix accounts and we discussed the project further. Was a very exciting 
meeting, we are narrowing in on scope, documenting bugs, and getting closer to getting this thing usable. We also discussed authentication and roles/permissions.

Additionally, we had our second real user sign up today on utahexpungements.org! The flyers seem to be working.

## 3/9/2019
Joel and Tucker met with Leonel Nieto to further discuss the CRM for Comunidades Unidas. Joel showed him progress on deploying the CRM to AWS via Elastic Beanstalk.
Joel also showed Leonel how to boot up the local environment and create database migrations for it. Next step is to meet again with Luis, Leonel, and Vicky to get
Wix access so that we can create a subdomain for the CRM on cuutah.org. Additionally we'll need a CU account on AWS for billing.

## 3/5/2019
Joel met with Leonel Nieto to show him a proof of concept demo of what we could build for Comunidades Unidas. We decided to use AWS so that we could use the $2,000
credit that CU has for being a nonprofit.

## 2/27/2019
Joel met with Luis Garza and Vicky Fuentes at Comunidades Unidas. It was decided that we would help build a CRM for Comunidades Unidas, starting with a client intake form.
The purpose of the CRM will be to organize information and to be able to report on what services Comunidades is providing to donors. Next step is to meet with Leonel Nieto,
who is a board member at CU who is fairly technical and has already started work on a database schema.

## 2/24/2019

Joel, Tucker, and I met yesterday and then Joel and I met again today to work on Docket Reminder stuff and a couple other things. Here's an update on those meetings.

Yesterday:
+ talked about possibility of growing a 501(c)(3) nonprofit out of our group
+ Joel updated us on some conversations he'd had with some contacts, and he's meeting with comunidades unidas this week
+ talked about what the "mission statement" would be -- criminal justice related or more general "do-gooding"
+ talked about consulting w/ nonprofits vs. more directly helping people

Today:
+ looked into & fixed a couple of Docket Reminder issues:
    + client sign up button was showing an orange-box error the first time clicked. this turned out to be related to a WP plugin called Akismet trying to block spam. we disabled Akismet and made sure ReCAPTCHA was still enabled, and it fixed the issue.
    + case number prefixes -- we were ignoring the three-char prefix before the case number, but we were previously making the (incorrect) assumption that ALL cases in the DB had this prefix. we fixed the code to be more flexible and work for cases with and without prefixes
    + did some database digging because David signed up for an email and never got a notification. turns out the case was in a different city/county than the one he signed up for, that's why there was no notification
+ Utah Expungements
    + I gave the flyers to Joel
    + for the lead collections on the main page, we noticed the email notifications weren't working so we redeployed the Firebase Cloud Function and now it works mysteriously
    + we added capturing of the sign up date to the lead collector
    + we fixed a button on the vocab page that was leading to a broken/empty page

## 2/19/2019

Leah made a SLC Justice specific page at docketreminder.com/slcjustice and david is meeting with the group at the court today to talk about next steps

## 2/11/2019

We printed 200 copies of the expungement flyer to distribute

## 2/4/2019

Leah and Tucker met with David McNeill and a group at the SLC justice court with Judge Landau about the Docket Reminder court appearance notification system:
Update on the meeting w/ Judge Landau and his group -- we showed them the docket reminder system for clients, talked about existing notification system efforts that have been made. A LOT of useful info gathered there, it was amazing. I'll paste my notes in here after this. We ended with basically a decision that they are going to create business cards with the URL and hand them out with ppl's paperwork as they're leaving the court, and they'll also make some announcements and tell people while they're waiting, etc. Super exciting! We are set to meet again in two weeks and the changes made by then will be: 1) create a specific signup page for SLC Justice court so people don't have to choose the stuff from the dropdown that might be confusing, 2) add the judge's name to the notification, and 3) (maybe) do some basic validation on the case number to check if it's in our system when they're signing up.

## 2/3/2019

We created a flyer for utah expungements site

## 1/30/2019

Ryan made a first draft of the video and posted it, the rest of us gave feedback

## 1/19/2019

- Leah finished the docket reminder stuff
- Leah and I changed the home page for utahexpungements.org to ask people to sign up for a "beta" and give us their email. The idea is that we can get a list of people who visit our site and see if we can help them more individually.

## 1/12/2019

Worked on slide deck / script for expungements video

## 12/17/2018

Leah's update:
I've been working on making some changes to the signup form for client court reminders on docketreminder.com. The main thing was to distinguish the case by court county/location. Last week I added those controls, but unfortunately this week as I started trying to make the backend changes, I realized there are problems with the way I was doing it. I was using "conditional groups" in the Wordpress plugin Contact Form 7 to render the dropdowns with the locations for each county. But it turns out the dropdowns are still _rendered_, just not visible -- a distinction that is important when it comes to the data that actually gets saved for the conditional dropdown (location). Anyway, I tried a few different solutions and none of them were working, so I decided to just write my own javascript to dynamically change the location dropdown when a county is picked. You can see that code here: https://gitlab.com/anitracks/courtclientalert/commit/5dc1251c3f512a4fde95b41a02bb0b7655e7b148. I'd be happy to answer any other questions too. Now the data is all being stored perfectly and I feel optimistic that the changes in the script on the backend will be quick and easy. (I may do them tonight, just wanted to write this down before I moved on.)
tl;dr I wrote this code: https://gitlab.com/anitracks/courtclientalert/commit/5dc1251c3f512a4fde95b41a02bb0b7655e7b148

## 12/10/2018

Leah's update:
I'm done for the night, but here is my update. I made all the updates to the form in the client alert stuff - justice/district radio, county dropdown, and filtered court location (city) dropdown. I haven't yet updated the script on the backend to actually respect this stuff when sending the notifications, so that'll have to wait. You can see the new signup page here: https://docketreminder.com/clientalert/

## 11-5-2018

Met at gourmandise
Talked about the election 
Joel got his record from the BCI, was empty though -- he talked to the employee there about expungements and learned that they were 7 months backlogged with processing the applications 
Tucker is going to shadow the application processing at BCI in an attempt to understand why it takes so long
Next steps: make the site more useful
- More content
- Some "onboarding" stuff?
- User testing?
Leah added a password reset flow to login
Ryan forgot to tip the server

## 10/15/2018

Leah's update:
+ goal is to get docket reminder client alerts working again after the switch to Dreamhost
+ the frontend functionality is all good, now just the send-notifications.py script needs to get run on a cron job
+ gave myself a cron refresher
+ confirmed that server is running python 2
+ confirmed that server has the courtclientalert repo cloned and therefore access to the send-notifications.py script
+ in setting up env variables, I realized that the email account we were using to send the notifications no longer exists because it was on Bluehost
+ so now we need to set up an email account using Dreamhost
+ researched email in Dreamhost, I need access to a UI portal which I don't currently have
+ sent David & Seth and email about the UI portal access

## 10/8/2018

Leah's update:
- docket reminder is now running a new theme with a child theme and all the custom templates are set up correctly
- the custom templates had to be changed for the new theme, and those were pushed to the gitlab repo
- there are still some issues to work out, but it looks like most of the functionality is restored for client alerts
- i had trouble with FTP access so i literally added a <?php touch(...) ?> script to a page and then VISITED the page exactly once to run the script and create files and then deleted the script lol

Joel's update:
- I fixed a bug where an extra blank page was being appended to all printed forms in Chrome

## 10/4/2018

Notes from meeting with Hollee for expungement clinic:

Affidavit - Would be nice to have the heading
Order Form would be nice to have done as soon as possible

We found out that it would be nice to have information from 
https://bci.utah.gov/criminal-records/obtain-a-copy-of-your-own-criminal-history-record/
before candidates come in for screening. This process to get a preliminary screening costs 15$ and will be a 'Better' check than self selecting.

Hollee mentioned that most candidates have trouble self reporting on their convictions, either they're embarrassed or they don't know, but the best way to get the correct screening from them is to have them get their BCI Criminal History report generated. They can use that report for filling out info on our site.

After the letter from BCI is dated and signed, eligible candidates have 90Days to get their case put together and filed. 

Next course of action: Finish the Motion, then work on the Affidavit.

## 10/2/2018

- We pelted Tucker with questions for two hours
- Landon made inappropriate jokes about murderers that were hilarious
- We're going to meet with Hollee on Thursday at 4:30 at the University of Utah to talk about people using our website at the monthly expungement clinic
- The team read Utah's law regarding sex offenses and what counts as a registerable offense. Tucker clarified the dark legal meaning of the word "mayhem"
- We figured out which forms we're going to work on next

## 9/25/2018

- Ryan is wrapping up the petition for expungement for conviction form
- I showed Luke how to build forms and we started on the petition for expungement of a drug conviction form
- I walked in on two adult women and a small child in the men's single bathroom at Tony Burgers

## 9/19/2018

Joel/Tucker email exchange:

Update from talking with Tucker:

My email:
```
Apologies for the slow response. That's interesting that attorneys have a special way to file documents that isn't accessible to the public. That gives us good direction on what to focus on.

Updates:
We're still building out the petition for conviction for and will move on to the Order, Request to Submit, and Fee Waiver forms.
Still working on building out the login experience and persisting/sharing data across forms. We've decided to split up the data into a "person" and a "case," with most of the data stored with the person and applicable to all cases, but some data stored on the case, which will be shared between all forms for the case but not between cases.
Questions:
Did Hollee get back to you?
Any update on if the courts are pursuing building a publicly accessible form filler outer? Or if they'd be interested in consulting with us on it?
Does next Monday work for you to come to one of our meetings? It would be 6:30 in Salt Lake. This week we're at Nostalgia Cafe, but we like hopping around and trying places.
With the Certificate of Eligibility, you explained they send you back a list of all of the things you are eligible to expunge, and you notify them which items on that list you'd like to pay for.  Then they send you the certificates you've requested." Is that back and forth (where you notify them which items on the list you'd like to pay for and then they send certificates) a formal process with forms that are filed? Or is it more informal? Is it via paper letter? In person visit to their office? What's the turnaround on actually getting the certificates? We'd love to see the paperwork from BCI that you mentioned earlier that you could show us.
The petition for expungement must be filled out once per case, right? (https://www.utcourts.gov/howto/expunge/docs/01_Petition_to_Expunge_Records_Criminal-conviction.pdf). And if you were convicted of multiple crimes all during one court proceeding, you would only need to submit one Petition?
Might be a lot to ask, but could you guide us through how someone gets filing fees waived? I've been looking at https://www.utcourts.gov/resources/forms/waiver/, but haven't been able to identify exactly which forms we can suggest getting the filing fees waived. Can this be done for any of the forms?  And https://www.utcourts.gov/resources/forms/waiver/docs/01_Motion_and_Affidavit_to_Waive_Fees.pdf and https://www.utcourts.gov/resources/forms/waiver/docs/02_Financial_Affidavit_Supporting_Motion.pdf.
```

Tucker's response:

```
Joel,
I did talk to Hollee.  She says she's usually really busy during the actual expungement clinics, but she'd be able to talk to you before one.  The next one would be October 4th, and if you could meet up with her around 430-445 or so she'd probably be able to talk.
I've honestly been busy with other projects, so I don't have much update here.  I can talk more about this project next time I see you.
That works!  That's actually pretty close to where I live so I can come by next Monday.
Good question.  It is somewhat formal – they send you basically a checkbox, with instructions on how to pay, so you can put in a credit card number and send it back.  I'm actually not sure what this turnaround time is like.  I can find out!
Yep, you've got it.  If they're convicted of multiple charges on one case, it's usually all counted as the same "criminal episode" so they just need one petition.  It is possible that a criminal episode can contain multiple cases, but that's super rare, and probably not worth worrying about.
I can definitely do that, but it might be something that's best done in person.  So I can walk you through it Monday when I come by.  Does that work?

Hope this helps!
```

## 9/17/2018

- Replied to Tucker's email with some more questions. Also invited Tucker to meet with us next week
- @Luke made the contributors page fancier. It now looks really nice.
- Ryan and I talked about the data model with person objects and case objects. And what data should be stored on which object. Also if we should even store credit card info on those things.
- I started work on the Motion to Waive Fees form
- I fixed a problem where print emulation in chrome dev tools looked weird
- Switched over to saving data to firebase once an input blurs.
- Switched over to in-memory answers being saved between forms (as long as you don't leave the app or refresh the page)
- Ryan and I got talking about bootcamps and bootcamp grads and businesses and hiring processes. It was fun :smile:

## 9/1/2018

Update from Joel:
"I just created four issues in our github project:

https://github.com/orgs/UtahAccessToJustice/projects/1

Also, I just sent an email to Tucker and Noella that i'll attach here
>>>We'd love to talk with or meet with the courts to discuss the possibility of an online process! Keep me updated on that.

Regarding utahexpungements.org, we're taking your feedback to heart and are shifting our focus to fillable forms and login.

Updates:
- Two new developers have joined our ranks, bringing us up to a total of 5 devs who are working on this a few hours each Monday.
- We've begun work on allowing users to save data once they login. What we have so far can be found at https://utahexpungements.org/app/login. We've only spent a few hours on it so once you login it doesn't actually do much, but the sign up and login themselves should be working.
- We started work on our next form, the Petition to Expunge Records (Conviction). It can be found at https://utahexpungements.org/app/forms/petition-for-conviction.
- We have created a new page, the "Form Bank," which lets you search for and fill out any form that we have available. It's at https://utahexpungements.org/app/forms. We're linking to the form bank on the home page now to try to encourage people.
- We have started work on the walkthrough/tutorial on filing a petition to expunge records.  What we have so far can be found at https://utahexpungements.org/app/file-petition.

Next things we'll do:
- Keep building out forms
- Keep building out the walkthrough/tutorial (TurboTax-like experience, hopefully).
- Keep building out the logged in user experience, including saving their info to a database when they fill out forms.

Questions:
- Could you introduce us to the attorneys who run the UofU's monthly expungement clinic? We'd like to talk with them and get their feedback on what we're doing. And ask them if it's something they would be interested in using as part of the clinic.
- We're thinking about how to best build out the login experience, and think that we will have two types of users: a lay person seeking an expungement for themself, or an attorney (maybe from expungement night) filling out forms with a client. We're considering introducing the concept of an "expungement engagement" or "case" or something similar, which would allow attorneys to view all the clients/cases they have worked on and keep the data for each client separate. However, it would be some more work for that and we wonder if maybe it would be better to start smaller by just allowing a logged in user to have one set of data that isn't silo'ed per "engagement." Any thoughts on this? This is one of the things we'd also like to talk to the people at the expungement clinic about.
- What forms would you recommend us working on next? What's the biggest bang for the buck? We've been using https://www.utcourts.gov/howto/expunge/#forms as our way to know about the forms, and right now we plan on going through the five different petitions for expungement. Is there something more useful to build out first?
- At some point, it might be fun for us to meet with you guys again. Thus far, I've been playing the role of evangelizing to the new devs and being the go-between, but I think it would be motivating for my team to meet you guys and have more of a firsthand relationship and experience."

## 8/27/2018

- english/spanish translation work
- login/signup with firebase
- worked more on forms
- some style fixes
- shared pictures of our cats while we worked from home

## 8/14/2018

LOTS of cops at tonyburgers
Emailed David & Seth back about hosting issues for docketreminder.com - we suggested staying with Bluehost and just deleting old scrape data
Worked on utahexpungements
- new header image and button styles
- more work on forms - credit card numbers!
- improvements to the screening tool

## 8/7/2018

- I emailed David and Seth about the last things remaining with docketreminder.com
- I emailed Noella and Tucker about utahexpungements.org
- Luke worked on improving the screening tool
- Luke and I shared a shake. They called it a two-cup shake.
- I worked more on implementing the Certificate of Eligibility form

## 7/23/2018

Tonyburger was out of veggie burgers!!! so we went to zupas

Docket Reminder client alert
- fixed issue with email and phone printing on confirmation page
- got confirmation texts through Twilio working!
- pushed the custom WP templates to the gitlab project
- they need to upgrade their Twilio account
- we fixed an issue where we weren't filtering out the Attorney signups and it was breaking the script
- we made some small tweaks to the notification system
- we fixed environment variables for the cron job

utah expungements
- might be building too much without getting any feedback
- we should send email to Noella and Tucker asking them for feedback
- worked on content for overview page

## 7/16/2018

we went to tonyburgers
- it was AMAZING

talking about the group
- who can we invite?

talking about possibly moving our meetings to SLC

what should we do tonight
- Leah: confirmation email and text for docket reminder
- Joel & Luke: get website in a decent place to show Tucker and Noella

translations
- Joel has set up the code so we can do english and spanish version

progress:
- translations are working
- eligibility tool has some more polish
- docket reminder confirmation email is working, still need to do confirmation SMS

## 7/9/2018

- I didn't take notes so this is just a summary
- I'm not Leah and my notes aren't as clever or fun to read
- Luke and I worked on utahexpungements.org. I put together some veererrry rudimentary routes for the app and will work this week on improving the design.
- Luke worked on the screening tool and pushed some code for it
- I worked on docketreminder.com. Here was my email to david:

Update from my team's work session tonight:
We (hopefully) fixed the issues where the cron job was throwing an error. Thanks Seth for forwarding me the emails with the error messages -- I was able to fix it and make sure the env variables are set correctly. I also stored the env variables in the .bashrc file. Unfortunately i don't know of a way of testing the actual cron job without waiting for tomorrow, but I'm hopeful it will work. If not, I've got something that almost definitely will work.
I changed the email subject to the new text you suggested.
"As of Mon Jul 02 2018 at 12:00 AM" -- 12:00am is just coming from the scrape_date column in the database. We thought it had a time in addition to the date, but it looks like it just has the date and so we ended up always printing midnight as the date. Our client alert script runs at 8am every morning, not at midnight. I have updated the email to just print out the day instead of the hour. Also it's now in the format "Monday, July 2, 2018" instead of "Mon Jul 02 2018"
I have updated the "Send" button to say "Sign up" instead.
Once again, I think I accidentally sent you a bunch of emails (although I don't think any texts went through) in my testing tonight.

Remaining things:
We still need to get back to you about how hard it would be to send the initial email/text confirming their sign up. I'll get back to you next week about it.
Leah is working on fixing the contact form -- there is a bug where it doesn't work unless you select "Both"
Before going live, the Twilio account needs to be set up with a credit card and upgraded from a free account. Otherwise, texts will fail to send to real clients.

## 6/28/2018

Ashly is here!!!! Yay!

David gave us the bluehost login and Twilio account!!!

Go over what we're working on
- Project 1: notifications for client court appearances
- Project 2: expungement tool
    - write stuff in a way that a layperson can understand

Ashly researched expungement stuff and started writing content for the website

Leah worked on getting Twilio SMS notifications working and refactoring the notification python script

Joel figured out email sending with bluehost, hooked up the user sign up database, and got the code deployed 

Next meeting on Monday!

## 7/02/2018

talked about feedback from david on docket reminder

talked about expungements
- we should have i18n in mind when we write the code
- once we have all the content, then we can approach a designer
    - Carly Moore
    - think about other designers?
    - student at dev mountain towards the end of their course, wanting to build out their portfolio?
- what's our vision for the site?
    - two calls to action: what is an expungement? start an expungement
    - left hand menu with 9 steps listed out, click on each one to get content
    - i18n controls
    - how to make it open source so others can edit
        - simple react components, markdown
- Bret - maybe figure out some i18n stuff
- doing expungements
    - one of the most important things is helping them fill out documents
        - itext - backend, license
        - not many open source tools to edit PDF
        - Joel's idea: 
            - we do a one-time conversion from PDF to SVG with some free tool, then render the SVG in the browser and place absolute-positioned fields, then try to get the browser to print it as separate 8.5x11 pages still
            - instructing users to print, and teaching them to save as PDF instead
            - this requires zero backend
            - can we create an 8.5x11 svg that prints correctly
    - good place to start is eligibility wizard
    - lookup/scrape data, iframe
        - more accurate than self-reported
        - account to do the lookup = money to sign up, and then money to do the lookup
    - navigation within expungement tool - sidebar

Bret: look into internationalization and content
Luke: look into the logic for eligibility and start on the self-reporting tool

Docket reminder

Joel: working on getting the updated code into GitLab and getting SMS unsubscribe to work
Leah: working on form validation -- required fields and valid phone and email, Email unsubscribe page

Progress!
- updated code is in GitLab
- you can now unsubscribe from SMS
- form validation: email or phone is required, email must be valid format, phone must be valid US format
- unsubscribe page is built that clears out user's email address (note: this is for ALL alerts, maybe want to revisit this if someone wants to unsubscribe from one particular case number?)


## 6/21/2018

JUSTIN IS HERE IT'S NOT A JOEL/LEAH ECHO CHAMBER ANYMORE

Expungements
- data for any conviction is public
    - have to get an account, get approved, then pay per search
- we went over the guidelines for eligibility and an overview of the expungement process
- tucker's dream is to have an expungement software tool and then contact the people in the database
    - 1/3 of convictions in his database are eligible to be expunged
    - most people don't get a lawyer for this process, and most people can't figure out the process, many don't know it's even possible
- tucker has an excel spreadsheet calculator with a sample of 1000, 320 are eligible
- idea for web app
    - there's a department of the court that builds a tool that allows you to fill out paperwork for the court, but they don't do expungements
        - if we can get with them and build it, it would be best
    - utah legal services - nonprofit - we could get them to host it, they've already got a website and a reputation
    - or, we could build our own
        - we can always do this at first and then move it over
        - two major aspects:
            - screening tool
            - paperwork
        - maybe we can start with the basic:
            - website with static content w/ 8 step process
            - slowly replace each step with tools
        - fill out forms
            - PDFs - potentially 65 documents per case
- technical details
    - login makes sense bc it's an 18 month process, gotta keep track of progress. but, the purpose is to remove all trace of your crime, so we should probably be aware of data security
    - maybe even login for static content so they can "check things off" like a to do list
- let's:
    - decide a name / domain
        - utahexpungements.com
    - create an AWS account and make preliminary tech stack decisions
    - maybe we can use github pages
        - with a custom domain

Justin had to leave, now it's a Joel/Leah echo chamber again

Smashburger breakkkkkkkk

Docket reminder project
- investigated the database
- everything looks manageable
- we wrote a python script that queried for the notifications and it's working! bc we are python and mysql GENIUSES


## 6/18/18

Update from Joel:

"I met with Tucker Samuelsen, who works for Noella Sudbury the Senior Policy Advisor on Criminal Justice for Salt Lake County, earlier this week about a new project for us to work on. The project is related to making it easier for people with criminal records to go through the legal process of getting their convictions expunged so that they won’t fail background checks when applying for jobs, housing, or government assistance.

It turns out that about a third of convictions on record haven’t been expunged yet, but could be. This ranges from felonies to misdemeanors to infractions. And the process for doing so is really convoluted (10+ pages of legal documents), takes about 18 months, and costs about $650 per conviction.

Tucker pointed out to me that as technology has improved in the last 30 years, one’s criminal record is becoming more and more accessible to employers and landowners, but that the technology to help the lay person expunge their record hasn’t really kept up. As a result, there are a lot of people who are essentially unemployable.

Anyway, enough soap boxing -- let’s talk some details. We are going to *_build a website_* that educates people on what expungements are and how to do them, then helps them know if their specific convictions qualify for expungement, and then helps them fill out the paperwork and instructs them how to file the paperwork.

We are not going to build all of that at once. Instead, we’ll start just with the part that helps people fill out the paperwork and expand from there. And we’ll work with Tucker, Noella, and the lawyers at Utah Legal Services (who provide free expungement legal aid) to make sure that we get it right and that people are aware that it exists."
    
## 6/14/2018

we got zupas again, leah got a mixture of cauliflower and tomato soup and it was better this time. also the strawberry was extra good, i think they're in season right now

how do we get more people to come
- we invited more people and followed up with people we have talked to previously

let's talk about the salt lake county thing briefly
- expungement screening tool
- Noella Sudbury - senior policy advisor - introduced us to Tucker Samuelson, the technical person
- they had an expungement day, and he helped her with the project
- expungement screening, and a tool to help prepare documents
    - once they think they qualify for an expungement, a tool to help them fill out the necessary paperwork
    - help people who could have their record expunged
- ideology: help people get their records expunged
    - justice system should be about rehabilitation, but a criminal record can set you back in a big way. and if the legal system allows expungement, then it should be an easy process that should be accessible to everyone

let's figure out the docket reminder stuff
- we still don't have a bluehost login
- we have their full database! yay!
- implementation
    - bluehost + WP
    - AWS + WP
    - AWS + not wordpress
- david and seth would consider switching from bluehost, but they like wordpress

OKAY LET'S WORK ON THE DOCKET REMINDER PROJECT
- we logged into the wordpress site and poked around the contact forms
- we figured out a way to get the contact form data to populate a database
- we adjusted the client alert form to be exactly what David told us - including terms and conditions
- we spent some time trying to import the 13GB SQL dump onto our local machines so we could start experimenting with queries
    - joel ran out of disk space and deleted GarageBand (RIP)
    - we learned about the "source" command in mysql
    - we figured out how to do it but it took 5ever


## 6/7/18

+ Wow it's our first meeting!
+ Ate Zupas. Soup was pretty good. Joel agrees.
+ Discussed the Docket Reminder project (docketreminder.com) 
    + Reviewed the 2 goals of the project:
        1. Create a page on the Wordpress site to automate sign up for clients
            + signup form with case number, name, email/phone so client can get notified about scheduled court appearance
        2. Automate the scraping/notification process with a cron job?
    + Progress is blocked because we don't have access to the database or hosting
    + Discussed rebuilding the site in a new stack if David & Seth are interested
    + Decided we should invite David to our meetings to get some more direction and make progress
+ Discussed goals of the group
    + Make progress on Docket Reminder project
        + Joel set up a call with David to get needed information and invite him to our meeting next week
    + Follow up with known leads for projects
        + Prescreening tool for expungements & reminder system for people to show up to court
            + Contact: Noelle Sudbury, director of Criminal Justice Advisory Council
            + Joel emailed her - she responded and was interested, we're trying to set up a time to meet with her
        + Salt Lake Legal data import w/ Justice Works
            + Joel emailed SLL
    + Find new leads for projects
    + Meet consistently on Thursday evenings in Lehi
        + Invite existing Slack members to join meetings
        + Pressure / guilt-trip people to show up
    + Post meeting notes to Slack channel
        + Done :sunglasses: 
    + Grow the group by reaching out to new people and inviting them to the Slack channel
        + Joel invited Ashley LaMarr to the Slack channel
+ Added Brendan Dassey emoji to Slack channel
