# AWS Systems Manager Compliance<a name="systems-manager-compliance"></a>

You can use Compliance, a capability of AWS Systems Manager, to scan your fleet of managed instances for patch compliance and configuration inconsistencies\. You can collect and aggregate data from multiple AWS accounts and Regions, and then drill down into specific resources that aren’t compliant\. By default, Compliance displays current compliance data about patching in Patch Manager and associations in State Manager\. \(Patch Manager and State Manager are also both capabilities of AWS Systems Manager\.\)

Patch compliance data from Patch Manager can be sent to AWS Security Hub\. Security Hub gives you a comprehensive view of your high\-priority security alerts and compliance status\. It also monitors the patching status of your fleet\. For more information, see [Integration with AWS Security Hub](security-hub-integration.md)\. 

The Compliance capability offers the following additional benefits and features: 
+ View compliance history and change tracking for Patch Manager patching data and State Manager associations by using AWS Config\.
+ Customize Compliance to create your own compliance types based on your IT or business requirements\.
+ Remediate issues by using Run Command, another capability of AWS Systems Manager, State Manager, or Amazon EventBridge\.
+ Port data to Amazon Athena and Amazon QuickSight to generate fleet\-wide reports\.

Compliance is offered at no additional charge\. You only pay for the AWS resources that you use\.

**EventBridge support**  
This Systems Manager capability is supported as an *event* type in Amazon EventBridge rules\. For information, see [Monitoring Systems Manager events with Amazon EventBridge](monitoring-eventbridge-events.md) and [Reference: Amazon EventBridge event patterns and types for Systems Manager](reference-eventbridge-events.md)\.

**Chef InSpec integration**  
Systems Manager integrates with [Chef InSpec](https://www.chef.io/inspec/)\. InSpec is an open\-source, runtime framework that enables you to create human\-readable profiles on GitHub or Amazon Simple Storage Service \(Amazon S3\)\. Then you can use Systems Manager to run compliance scans and view compliant and noncompliant instances\. For more information, see [Using Chef InSpec profiles with Systems Manager Compliance](integration-chef-inspec.md)\.

**Pricing**  
Compliance is offered at no additional charge\. You only pay for the AWS resources that you use\.

**Topics**
+ [Getting started with Compliance](sysman-compliance-prereqs.md)
+ [Creating a resource data sync for Compliance](sysman-compliance-datasync-create.md)
+ [Working with Compliance](sysman-compliance-about.md)
+ [Remediating compliance issues using EventBridge](sysman-compliance-fixing.md)
+ [Compliance walkthrough \(AWS CLI\)](sysman-compliance-walk.md)