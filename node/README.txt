DESCRIPTION
--------------------------
The message_ui_node module contains the functionality to log activity
performed on nodes.
The activity that can be logged is:
- insert
- update
- delete

The activity is logged using the message module.
See http://drupal.org/project/message


USAGE
--------------------------
Enabling the activity logging can be set per content type and per activity.
See the node type settings for the content type you want to enable the activity
logging.

NOTE: The message module deletes by default all node messages when a node is
deleted. You can disable this trough /admin/config/system/message.


DISABLE ACTIVITY LOGGING
--------------------------
Some scripts (e.g. batch actions) can require that no activity is logged. You
can temporarily disable this by using the disable method:

message_ui_comment_message_disable();

This will disable the activity logging only during the current page request.
Disabling is not persistent between requests.

You can enable the activity logging using:

message_ui_comment_message_enable();


ACTIVITY MESSAGES
--------------------------
This module defines the message types used to log the activity.
This messages can be changed using the message interface:
/admin/structure/messages

The following message types are defined:
- node_insert : when a node is created.
- node_update : when a node is updated.
- node_delete : when a node is deleted.

NOTE: an update will only be logged if:
- The update is done by somebody else then the person who did the last update.
- If the new update, done by the same as the last user, is done 6 hours later
  then the previous update.
