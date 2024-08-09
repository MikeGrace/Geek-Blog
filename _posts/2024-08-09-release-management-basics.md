---
title: "Release Management Basics"
layout: post
categories:
  - SDLC
---

Good release management is balancing system integrity with getting new features and fixes to customers at speed. Good release management is also agile, adjusting as your teams and system change. How can you make sure that your features are getting to production as quickly as possible with the least amount of friction and risk as possible? How do you know when you are maintaining a healthy balance? Use this high-level guide help identify where your teams may have opportunities to improve.

## Ensuring System Integrity

System integrity is Non-Negotiable. Compromises in system integrity:

- Risks revenue  
- Degrades the customer experience
- Wastes engineering time
- Breaks momentum
  
## Testing

Testing attempts to ensure that changes are working as expected without negative side effects.

- Unit Testing: Does our local code change do what we think it should?
- Integration Testing: Are components working together?
- End-to-End Testing: Does the system work as a whole?
- Regression Testing: Are we breaking existing functionality?

## Monitoring and Alerting

Your system is designed to accomplish specific business objectives. Those outcomes and the state and activity required to accomplish those need to be monitored. This allows you to learn from the past to prepare for the future as well as helping with investigations when things go wrong.

Based on your monitoring, you should be able to set up alerting for performance degradation and errors. This allows you to reduce the time to identifying and resolving any issues that do come up as well as less time and stress constantly trying to check on things to see if they are failing.

Centralized log aggregation can also reduce time and friction experienced in identifying root causes.

## Feature Release Strategies

Blue-Green Deployments: If you can configure your environment to be able to flip back and forth between environments serving production, it's nice and quick.

Canary Releases: Rolling out changes to a subset of users is a great way to reduce how many users would be impacted by a broken deployment.

Feature Toggles: Code changes get deployed but the feature is turned off for users. This approach decouples production code changes from the actual release of features to customers. This allows for many smaller production deployments instead of needing a single large deployment to release a large feature.

## Backup and Recovery

Regular Backups: If you don't have backups of your data and systems that you can restore from, you aren't being serious.

![stop it, get some help animated gif](assets/2024/08/2024-08-09-stop-it-get-some-help-small.gif)

Disaster Recovery: Do you have a plan for recovering from a worst-case scenario? The more dependencies you have on other systems and code bases, the more you should be investing in a disaster recovery plan. [https://dependencystrike.com/](https://dependencystrike.com/)

Rollback Procedures: If something goes wrong, how do we undo the deployment?

## Change Management

This is the gate that all production changes go through. It’s a checkpoint that reflects the priorities of the business. When done well, change management will promote behavior that leads to quality production deployments, reduce stress, improve trust and predictability all while not adding too much overhead. When done poorly it will increase costs by slowing down production deployments, lower team moral, promote shortcut behavior or may even get ignored.

Change Approval Process: Who has the final say in letting a change through to production or if it needs adjustments or delay? What is the criteria for approval or rejection? Why?

Pre-Deployment Reviews: Have others on the team had a chance to review what is being changed and how? Has the impact of this change been identified? Is there sufficient test coverage with the tests that were run? Has appropriate documentation been updated related to this change?

### Change Ticket

Everything up to this point is going to be destilled down into a single change artifact called a change ticket. When done well, this single ticket will be an effective communication tool and help guide everyone through the production change. What information is put into a change ticket is going to depend on different factors but there are a few fields that should be consistent across organizations.

#### Title or Short Description

This is usually the very first thing that anyone will see. It should be a single sentence. It should describe what is being changed.

**Prompts to help distill information**

- What is changing?
- What part of the system is changing?
  

**Source inputs**

- Code change 

Anyone reading this short description should be able to determine if this is something they can ignore or if they need to spend the time to dig into the details. It's wild to think that hundreds or thousands of hours are being distilled down into a dozen or so words.

#### Description

Expanding on the title, the description can give more details on what is changing and what parts of the system. If the change ticket system doesn't have a specific way to link back to work tickets, this is a good place to paste links to all the related work tickets (Jira).

**Prompts to help distill information**

- What details are business leaders and team members going to need to know to understand what is changing?
- Where in the system is the change being made?
- What user experience does this impact?
- Can you explain this in layman's terms?

**Source inputs**

- Code change

This description should give stakeholders a pretty clear idea of what this change is doing, where it is happening, and how it is going to impact the system.

#### Justification

This lets everyone know why the change is being done. That might be business leaders, the support team, the change approver, other engineering teams, and even end users.

**Prompts to help distill information**

- What value comes from deploying this change?
- What is the impact if we don't deploy?
- Why is the change needed?
- How does this change get us closer to a business goal?

**Source inputs**

- Business goals
- Product priorities
- Sprint goals
- Code change
- User journey

The exciting aspect of justification is that it ties together business goals, engineering work, and customer experience into a single field. Are your engineers able to easily identify how this change will help reach the business goals? If yes, congratulations! You have clear business goals. The goals have been communicated through the company, surviving the game of telephone. Now the engineers are able to see how their work directly contributes to the business and communicate that out clearly. If not, are we trying to deploy something that is a distraction and isn't what the business wants to be focused on? Is it the right thing but we don't have clear business goals set or well communicated?

#### Deployment Steps

**Prompts to help distill information**

- What are all of the steps or actions that need to be taken to deploy successfully?
- How would you document the steps for a new hire?
  

**Source inputs**

- Code change
- Release strategies

Are your deployment steps short and easy? Congratulations! You likely have tools and processes in place that make deployments automated and repeatable. Are your engineers complaining about having to write out all of the steps to do a deployment? You have just discovered an area where you may need to simplify and/or automate deployment steps. The more complicated and more steps there are, the more friction and risk involved with each deployment.

#### Rollback Steps

**Prompts to help distill information**

- *Similar to deployment steps*
  

**Source inputs**

- Code chanage
- Release strategies
- Backup and recovery plans/systems

#### Validation Steps

**Prompts to help distill information**

- How would an end user know if the deployment was successful?
- How would our monitoring and alerting indicate if this deployment was successful?
- What are all of the steps or actions that need to be taken to confirm the deployment was successful?

**Source inputs**

- Code change
- Monitoring and alerting
- Testing
- User journey
- Business goals

The holy grail is having a system configured in a way that production changes are automatically rolled back if any automated tests fail. Have good validation steps will reduce the time needed to discover failed deployments. If engineers can validated a deployment is good quickly, they can move on to the next task sooner.

#### Other Fields

Other fields that are usually found on a change ticket.

- Change ID: a way to reference this particular change.
- Risk level: qualitative and/or quantitative measure of how risky this change is.
- Validator: who is responsible for validating the deployment.
- Assignee: who is responsible for carrying out the deployment.
- Schedule: target start and end date and times.
- State: reviewed, approved, deploying, validating, closed, etc.
- Notes: place to capture notes relevant to deployment effort.

## Conclusion

Release management isn't just about creating and managing change tickets or getting code into production, it's about moving as fast as possible while keeping risks within acceptable limits. Effective release management ties changes directly to business goals and customer outcomes. It serves as a vehicle for clear communication with stakeholders, outlining what is changing, why, when, how, the associated risks, and how those risks are being mitigated. All of this builds trust and collaboration, enabling you and your team to move faster, operate more efficiently, and achieve remarkable results.