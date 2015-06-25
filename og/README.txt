DESCRIPTION
--------------------------
The message_ui_og module contains the functionality to log activity related to
group memberships.
The activity that can be logged is:
- request : a user requests membership to a group.
- approve : a user membership request is approved.
- reject  : a user membership request is rejected.
- join    : a user joins a group (also triggered when a membership request is
            approved.
- leave   : a user leaves a group (membership deleted by user).
- remove  : a user group membership was deleted by somebody else then the user.
- revoke  : a user deletes his non approved membership request.
- block   : a group membership status was changed to blocked.
- unblock : a blocked group membership status is changed to active.

The activity is logged using the message module.
See http://drupal.org/project/message


USAGE
--------------------------
Enabling the activity logging can be set per group content type and per activity.
See the node type settings for the content type you want to enable the activity
logging.

The settings will only be displayed on node types set as Group types. Make the
node first a group. The OG activity options become available from the moment the
node settings are saved with the Node as Group activated.

NOTE: The message module deletes by default all node messages when a node is
deleted. You can disable this trough /admin/config/system/message.


DISABLE ACTIVITY LOGGING
--------------------------
Some scripts (e.g. batch actions) can require that no activity is logged. You
can temporarily disable this for this module by using the disable method:

message_ui_og_message_disable();

This will disable the activity logging only during the current page request.
Disabling is not persistent between requests.

You can enable the activity logging using:

message_ui_og_message_enable();


ACTIVITY MESSAGES
--------------------------
This module defines the message types used to log the activity.
This messages can be changed using the message interface:
/admin/structure/messages

The following message types are defined:
- message_ui_og_request : a user requests membership to a group.
- message_ui_og_approve : a user membership request is approved.
- message_ui_og_reject  : a user membership request is rejected.
- message_ui_og_join    : a user joins a group (also triggered when a
                            membership request is approved.
- message_ui_og_leave   : a user leaves a group (membership deleted by user).
- message_ui_og_remove  : a user group membership was deleted by somebody else
                            then the user.
- message_ui_og_revoke  : a user deletes his non approved membership request.
- message_ui_og_block   : a group membership status was changed to blocked.
- message_ui_og_unblock : a blocked group membership status is changed to
                            active.
