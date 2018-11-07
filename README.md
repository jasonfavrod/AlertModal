# AlertModal
A Bootstrap-Vue Component for User Alerts.

Props
-----
Variables that can be passed to the component.

* `modal_id`          - The HTML id of the modal.

### Volitile Props
The following `props` values are cleared when the modal is hidden.

* `message`           - The message displayed to the user.
* `header`            - The modal header.

#### Bug Report Props
Set the following `props` to provide users with an option to send a bug report.
These `props` are also _volitile_, meaning they are cleared when the modal is hidden.

The bug report option comes in the form of a button on the AlertModal. When pressed,
the user's configured email client is launched.

* `bug_report_email`    - Set this to the email where to send the bug report.
* `bug_report_subject`  - The subject of the bug report email.
* `bug_report_message`  - The body of the bug report email.
