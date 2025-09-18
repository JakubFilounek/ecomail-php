# PHP wrapper for Ecomail API

[![Build Status](https://travis-ci.org/Ecomailcz/ecomail-php.svg?branch=master)](https://travis-ci.org/Ecomailcz/ecomail-php)
[![Downloads this Month](https://img.shields.io/packagist/dm/ecomailcz/ecomail.svg)](https://packagist.org/packages/ecomailcz/ecomail)

# Instalation

```shell
composer require ecomailcz/ecomail
```

# Usage

```php
$ecomail = new Ecomail('API_KEY');
$ecomail->getListsCollection();
```

When there are more results, you will get `last_page` parameter in your response, which you can then use in another request.

```php
$ecomail->page(2)->getListsCollection();
```


You will find your API key in your account in "integrations" section.

# Available methods

All methods return: `array|stdClass|string`

For more detailed documentation please visit: https://ecomailczv2.docs.apiary.io/

## List and Subscriber Management

### getListsCollection()
Get all lists in the account.

### addListCollection(array $data)
Create a new subscriber list.

### showList($list_id)
Get detailed information about a specific list.

### updateList($list_id, array $data)
Update an existing list.

### getSubscribers($list_id)
Get subscribers from a specific list.

### getSubscriber($list_id, $email)
Get a specific subscriber from a list by email.

### getSubscriberByPhone($list_id, $phone)
Get a specific subscriber from a list by phone number.

### getListSegments($list_id)
Get segments for a specific list.

### getSubscriberList($email)
Get subscriber information by email (global).

### addSubscriber($list_id, array $data)
Add a new subscriber to a list.

### removeSubscriber($list_id, array $data)
Remove subscriber from a list.

### updateSubscriber($list_id, array $data)
Update subscriber information in a list.

### addSubscriberBulk($list_id, array $data)
Add multiple subscribers to a list at once.

### deleteSubscriber($email)
Remove subscriber from database (all lists).

### getSubscriberByEmail($email)
Get subscriber information by email (global).

## Campaigns

### listCampaigns($filters = null)
Get all campaigns, optionally filtered.

### addCampaign(array $data)
Create a new campaign.

### updateCampaign($campaign_id, array $data)
Update an existing campaign.

### sendCampaign($campaign_id)
Send a campaign immediately.

### getCampaignStats($campaign_id)
Get campaign statistics.

### getCampaignStatsDetail($campaignId, $queryParams = array())
Get detailed campaign statistics with optional filters.

### getSegmentStats($segmentId)
Get segment statistics across all campaigns.

## Automation

### listAutomations()
Get all automation pipelines.

### triggerAutomation($automation_id, array $data)
Trigger an automation for a specific email.

### getPipelineStats($pipelineId)
Get automation pipeline statistics.

### getPipelineStatsDetail($pipelineId, $queryParams = array())
Get detailed automation pipeline statistics.

### getPipelineStatsForMultipleEmails($pipelineId, array $data, $queryParams = array())
Get automation statistics for multiple emails.

## Templates

### createTemplate(array $data)
Create a new email template.

### getTemplate($templateId)
Get template by ID.

## Domains

### listDomains()
Get all verified domains.

### createDomain(array $data)
Add a new domain for verification.

### deleteDomain($id)
Delete a domain.

## Transactional Emails

### sendTransactionalEmail(array $data)
Send a transactional email.

### sendTransactionalTemplate(array $data)
Send a transactional email using a template.

### getTransactionalStats()
Get transactional email statistics.

### getTransactionalStatsDOI()
Get double opt-in email statistics.

## Transactions

### createNewTransaction(array $data)
Create a new transaction record.

### createBulkTransactions(array $data)
Create multiple transactions at once.

### getTransactions(array $queryParams = array())
Get transactions with optional filters.

### updateTransaction($transaction_id, array $data)
Update an existing transaction.

### deleteTransaction($transaction_id)
Delete a transaction.

### deleteBulkTransactions(array $data)
Delete multiple transactions at once.

## Feeds

### refreshProductFeed($feedId)
Refresh a product feed.

### refreshDataFeed($feedId)
Refresh a data feed.

## Tracker

### addEvent(array $data)
Add a tracking event.

## Search

### search($query)
Search for a subscriber by email address.

## Discount Coupons

### importCoupons(array $data)
Import discount coupons.

### deleteCoupons(array $data)
Delete discount coupons.

## Webhook

### setWebhook(array $data)
Set webhook URL for receiving campaign events.

### getWebhook()
Get current webhook URL.

### deleteWebhook()
Delete webhook URL.

