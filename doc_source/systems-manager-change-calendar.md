# AWS Systems Manager Change Calendar<a name="systems-manager-change-calendar"></a>

Change Calendar, a capability of AWS Systems Manager, lets you set up date and time ranges when actions you specify \(for example, in [Systems Manager Automation](systems-manager-automation.md) runbooks\) might or might not be performed in your AWS account\. In Change Calendar, these ranges are called *events*\. When you create a Change Calendar entry, you're creating a [Systems Manager document](sysman-ssm-docs.md) of the type `ChangeCalendar`\. In Change Calendar, the document stores [iCalendar 2\.0](https://icalendar.org/) data in plaintext format\. Events that you add to the Change Calendar entry become part of the document\.

A Change Calendar entry can be one of two types:

**`DEFAULT_OPEN`**, or Open by default  
When a calendar entry is open by default, actions can run by default, but are blocked from running during associated events\. During events, the state of a `DEFAULT_OPEN` calendar is `CLOSED`\.

**`DEFAULT_CLOSED`**, or Closed by default  
When a calendar entry is closed by default, actions that are tracking Change Calendar don't run by default, but can run during events associated with the calendar entry\. During events, the state of a `DEFAULT_CLOSED` calendar is `OPEN`\.

## Who should use Change Calendar?<a name="systems-manager-change-calendar-who"></a>
+ Any Amazon Web Services customer who creates or runs Automation runbooks, creates change requests in Change Manager, or creates associations in State Manager\. \(Automation, Change Manager, and State Manager are all capabilities of AWS Systems Manager\.\) By integrating these capabilities with Change Calendar, you can allow or block these three action types depending on the current state of the change calendar you associate with each one\.
+ Administrators who are responsible for keeping the configurations of Systems Manager managed instances consistent, stable, and functional\.

## Benefits of Change Calendar<a name="systems-manager-change-calendar-benefits"></a>

The following are some benefits of Change Calendar\.
+ **Review changes before they're applied**

  A Change Calendar entry can help ensure that potentially destructive changes to your environment are reviewed before they're applied\.
+ **Apply changes only during appropriate times**

  Change Calendar entries help keep your environment stable during event times\. For example, you can create a Change Calendar entry to block changes when you expect high demand on your resources, such as during a conference or public marketing promotion\. A calendar entry can also block changes when you expect limited administrator support, such as during vacations or holidays\. You can use a calendar entry to allow changes except for certain times of the day or week when there is limited administrator support to troubleshoot failed actions or deployments\.
+ **Get the current or upcoming state of the calendar**

  You can run the Systems Manager `GetCalendarState` API operation to show you the current state of the calendar, the state at a specified time, or the next time that the calendar state is scheduled to change\.
+ 

**EventBridge support**  
This Systems Manager capability is supported as an *event* type in Amazon EventBridge rules\. For information, see [Monitoring Systems Manager events with Amazon EventBridge](monitoring-eventbridge-events.md) and [Reference: Amazon EventBridge event patterns and types for Systems Manager](reference-eventbridge-events.md)\.

**Topics**
+ [Who should use Change Calendar?](#systems-manager-change-calendar-who)
+ [Benefits of Change Calendar](#systems-manager-change-calendar-benefits)
+ [Setting up Change Calendar](systems-manager-change-calendar-prereqs.md)
+ [Working with Change Calendar](systems-manager-change-calendar-working.md)
+ [Adding Change Calendar dependencies to Automation runbooks](systems-manager-change-calendar-automations.md)