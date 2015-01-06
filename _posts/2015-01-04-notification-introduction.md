## notification introduction

### notification 
1. notification overview
   - notification elements
        * title
        * body
        * contacts
        * settings
   - oldAware broadcast engine introduction (see broadcast.jpg)
2. front-end view
   - send notification
        * Standard
        * Polling
        * Conference
   - notification launch policy
        * SendNow
        * Schedule
        * Recurring
   - notification template
   - message template
   - active/history notication list
   - notification event
   - quick report
        * notification summary
        * event analysis
        * detailed notification analysis
        * escalation summary
   - custom report
        * notifications
        * incident notifications
3. more features and functionalities
   - cross org notification
   - escalation notification
   - rtf support for email path (rich text format)
   - publish options
        * Everbrige Network
        * CMAS/WEA
        * AlertUs
        * Web Posting
   - incident notifications
4. notification back-end implementation (NotificationServiceImpl and NotificationManagementServiceImpl)
   - models
        * Notification
        * BroadcastTemplate (BroadcastSettings/BroadcastContacts)
        * LaunchPolicy
        * BatchNotification
        * BatchBroadcastTemplate
   - notification send flow
        * notificationTask
        * launchLog
        * escalationNotificationTask
   - notification status tracking
        * statusTracker
   - NotificationService interfaces
        * sendNotification
   - NotificationManagementService interfaces (spring quartz jobs)
        * processSendNotifications
        * processRecurringNotfications
        * processEscalationNotificationTasks
        * processTrackNotificationStatus
   - send to Aware (BroadcastService.sendBroadcast)

### notification report (can be configured to each of the following implemenation through dataCenter collection on org level)
1. DispatcherService interfaces - used by both implementations
   - addTransmitLogBatch
   - generateServerNodeIndex
   - addReportLogTask
   - addContactLogTask
   - refreshNodeCount
   - monitorServerNode

2. mongodb implementation
   - collections
        * notificationReportLog
   - models
        * NotificationReportLog
        * ReportLogTask
        * TransmitLog
   - interfaces (TransmitLogService)
        * distributeReportLogTask
        * createNotificationReportLog
        * distributeTransmitLog
        * processTransmitLog
        * handleNotPreparedTransmitLog

3. elasticsearch implemetation
   - collections
        * active report in mongodb (notificationLog and contactLog collection)
        * history report (in elasticsearch, notification_log and contact_log type under index report_log)
   - models
        * NotificationLog
        * ContactLog
        * ContactLogTask
        * AttemptLog
   - interfaces (ResultProcessService)
        * distributeContactLogTask
        * createContactLog
        * distributeAttemptLog
        * processAttemptLog
        * handleNotPreparedTransmitLog
        * handleError
