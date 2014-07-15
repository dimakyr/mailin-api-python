# SendinBlue Python API

This is the SendinBlue python API wrapper. 
You will need to install the following module
* httplib2

## Quickstart

1. You will need to first get the Access key and Secret key from [SendinBlue](https://www.sendinblue.com).

2. Assuming that you have cloned this git repo, or downloaded mailin.py . You can use this small sample script to get started
```python
from mailin import Mailin
m = Mailin("https://api.sendinblue.com/v1.0","access key","secret key")
campaigns = m.get_campaigns('')
```
3. To explore more, you should visit the [SendinBlue API documentation](https://apidocs.sendinblue.com).

## Available functions

### Campaign calls

 * [get_account](https://apidocs.sendinblue.com/account/)() - Get your account information
 * [create_child_account](https://apidocs.sendinblue.com/account/#2)(email,password,company_org,first_name,last_name,credits) - Create a Reseller child account
 * [update_child_account](https://apidocs.sendinblue.com/account/#3)(child_authkey,company_org,first_name,last_name,password) - Update a Reseller child account
 * [delete_child_account](https://apidocs.sendinblue.com/account/#4)(child_authkey) - Delete a Reseller child account
 * [get_child_account](https://apidocs.sendinblue.com/account/#5)(child_authkey) - Get Reseller child accounts
 * [add_remove_child_credits](https://apidocs.sendinblue.com/account/#6)(childauthkey,add_credits,remove_credits) - Add/Remove Reseller child credits
 * [get_campaigns](https://apidocs.sendinblue.com/campaign/#1)(type) - Get list of all campaigns or of specific type: "classic", "trigger", "sms"
 * [get_campaign](https://apidocs.sendinblue.com/campaign/#1)(id) - Get specific campaign object
 * [create_campaign](https://apidocs.sendinblue.com/campaign/#2)(category,from_name,name,bat_sent,html_content,html_url,listid,scheduled_date,subject,from_email,reply_to,to_field,exclude_list) - Create a campaign
 * [delete_campaign](https://apidocs.sendinblue.com/campaign/#3)(id) - Delete a campaign
 * [update_campaign](https://apidocs.sendinblue.com/campaign/#4)(id,category,from_name,name,bat_sent,html_content,html_url,listid,scheduled_date,subject,from_email,reply_to,to_field,exclude_list) - Update campaign information
 * [campaign_report_email](https://apidocs.sendinblue.com/campaign/#5)(id,lang,email_subject,email_to,email_content_type,email_bcc,email_cc,email_body) - Sending reports to specific emails
 * [campaign_recipients_export](https://apidocs.sendinblue.com/campaign/#6)(id,notify_url,type) - Export recipients of a campaign
 * [send_bat_email](https://apidocs.sendinblue.com/campaign/#7)(campid,email_to) - Send a test Email (bat)
 * [create_trigger_campaign](https://apidocs.sendinblue.com/campaign/#8)(category,from_name,name,bat_sent,html_content,html_url,listid,scheduled_date,subject,from_email,reply_to,to_field,exclude_list,recurring) - Create a trigger campaign
 * [update_trigger_campaign](https://apidocs.sendinblue.com/campaign/#9)(id,category,from_name,name,bat_sent,html_content,html_url,listid,scheduled_date,subject,from_email,reply_to,to_field,exclude_list,recurring) - Update trigger campaign information
 * [campaign_share_link](https://apidocs.sendinblue.com/campaign/#10)(campaign_ids) - Get campaign share link
 * [update_campaign_status](https://apidocs.sendinblue.com/campaign/#11)($id,$status) - Modify a campaign status
 * [get_folders](https://apidocs.sendinblue.com/folder/#1)() - Get list of all the folder details.
 * [get_folder](https://apidocs.sendinblue.com/folder/#2)(id) - Get all the folder details for folder with id <id>
 * [create_folder](https://apidocs.sendinblue.com/folder/#3)(name) - Create a folder
 * [delete_folder](https://apidocs.sendinblue.com/folder/#4)(id) - Delete folder with folder id <id>
 * [update_folder](https://apidocs.sendinblue.com/folder/#5)(id,name) - Update folder with folder id <id>
 * [get_lists](https://apidocs.sendinblue.com/list/#1)() - Get all the lists
 * [get_list](https://apidocs.sendinblue.com/list/#2)(id) - Get information about a list
 * [create_list](https://apidocs.sendinblue.com/list/#3)(list_name,list_parent) - Create a list
 * [delete_list](https://apidocs.sendinblue.com/list/#4)(id) - Delete a list
 * [update_list](https://apidocs.sendinblue.com/list/#5)(id,list_name,list_parent) - Updating a list
 * [add_users_list](https://apidocs.sendinblue.com/list/#6)(id,users) - Add users to a list
 * [delete_users_list](https://apidocs.sendinblue.com/list/#7)(id,users) - Delete users from a list
 * [get_attributes](https://apidocs.sendinblue.com/attribute/#1)() - Listing all attributes
 * [get_attribute](https://apidocs.sendinblue.com/attribute/#2)(type) - Listing a certain type attributes
 * [create_attribute](https://apidocs.sendinblue.com/attribute/#3)(type,data) - Creating attributes
 * [delete_attribute](https://apidocs.sendinblue.com/attribute/#4)(type,data) - Deleting attributes
 * [get_user](https://apidocs.sendinblue.com/user/#2)(id) - Get information about a user/email
 * [create_update_user](https://apidocs.sendinblue.com/user/#1)(email,attributes,blacklisted,listid,listid_unlink) - Create/Update a user information
 * [delete_user](https://apidocs.sendinblue.com/user/#4)(id) - Deleting user from db is not permitted but this action will unlink him from all lists
 * [import_users](https://apidocs.sendinblue.com/user/#5)(url,listids,notify_url,name) - Import users/emails
 * [export_users](https://apidocs.sendinblue.com/user/#6)(export_attrib,filter,notify_url) - Export users/emails
 * [get_processes](https://apidocs.sendinblue.com/process/#1)() - Get information about all background processes
 * [get_process](https://apidocs.sendinblue.com/process/#2)(id) - Get information about a specific process
 * [get_senders](https://apidocs.sendinblue.com/sender-management/#1)(option) - Get information about all/specific senders
 * [create_sender](https://apidocs.sendinblue.com/sender-management/#2)(sender_name,sender_email,ip_domain) - Create a sender
 * [delete_sender](https://apidocs.sendinblue.com/sender-management/#3)(id) - Delete a sender
 * [update_sender](https://apidocs.sendinblue.com/sender-management/#4)(id,sender_name,sender_email,ip_domain) - Update a sender

### SMTP calls

 * [get_report](https://apidocs.sendinblue.com/report/)(limit,start_date,end_date,offset,date,days,email) - Retrieve information for all report events
 * [get_statistics](https://apidocs.sendinblue.com/statistics/)(aggregate,tag,days,end_date,start_date) - Get aggregate statistics about emails sent
 * [get_webhooks](https://apidocs.sendinblue.com/webhooks/#1)() - List registered webhooks
 * [get_webhook](https://apidocs.sendinblue.com/webhooks/#2)(id) - Get information about a webhook
 * [create_webhook](https://apidocs.sendinblue.com/webhooks/#3)(url,description,events) - Registering a webhook
 * [delete_webhook](https://apidocs.sendinblue.com/webhooks/#5)(id) - Deleting a webhook
 * [update_webhook](https://apidocs.sendinblue.com/webhooks/#4)(id,url,description,events) - Editing a webhook
 * [delete_bounces](https://apidocs.sendinblue.com/bounces/)(start_date,end_date,email) - Deleting bounces
 * [send_email](https://apidocs.sendinblue.com/tutorial-sending-transactional-email/)(to,subject,from_name,html,text,cc,bcc,replyto,attachment,headers) - Sending out a transactional email
 * [send_transactional_template](https://apidocs.sendinblue.com/template/)(id,to,cc,bcc,attr) - Send templates created on Sendinblue, through Sendinblue smtp.
 * [create_template](https://apidocs.sendinblue.com/template/#2)(from_name,name,bat_sent,html_content,html_url,subject,from_email,reply_to,to_field,status) - Create a template 
 * [update_template](https://apidocs.sendinblue.com/template/#3)(id,from_name,name,bat_sent,html_content,html_url,subject,from_email,reply_to,to_field,status) - Update template information

### SMS calls

 * [send_sms](https://apidocs.sendinblue.com/sms/)(to,from_name,text,web_url,tag,type) - Sending a SMS
 * [create_sms_campaign](https://apidocs.sendinblue.com/mailin-sms/#2)(camp_name,sender,content,bat_sent,listids,exclude_list,scheduled_date) - Create a SMS campaign
 * [update_sms_campaign](https://apidocs.sendinblue.com/mailin-sms/#3)(id,camp_name,sender,content,bat_sent,listids,exclude_list,scheduled_date) - Update a SMS campaign
 * [send_bat_sms](https://apidocs.sendinblue.com/mailin-sms/#4)(campid,mobilephone) - Send a test SMS campaign

## Install

To install the `mailin` module you can run `python setup.py install` in the root of the distribution.

### Dependencies

To just install the dependencies run `pip install -r requirements.txt`
