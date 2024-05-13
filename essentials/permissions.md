---
description: Plugin Permission List
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
---

# 📃 Permissions



{% hint style="info" %}
`true` - All players have the permission by default

`op` - Only operators have the permission by default

`false` - No players have the permission by default
{% endhint %}

<table data-full-width="true"><thead><tr><th width="308">Permission</th><th width="576">Description</th><th>Default</th></tr></thead><tbody><tr><td><code>melodymine.*</code></td><td>Permission granting access to all Melodymine commands.</td><td><code>op</code></td></tr><tr><td></td><td><strong>Children</strong></td><td></td></tr><tr><td></td><td><code>melodymine.admin</code></td><td></td></tr><tr><td><code>melodymine.admin</code></td><td>Melodymine admin permission.</td><td><code>op</code></td></tr><tr><td></td><td><strong>Children</strong></td><td></td></tr><tr><td></td><td><code>melodymine.reload</code></td><td></td></tr><tr><td></td><td><code>melodymine.adminmode</code></td><td></td></tr><tr><td></td><td><code>melodymine.mute</code></td><td></td></tr><tr><td></td><td><code>melodymine.unmute</code></td><td></td></tr><tr><td></td><td><code>melodymine.toggle</code></td><td></td></tr><tr><td><code>melodymine.start</code></td><td>Grants the ability to obtain the website link to establish a voice connection.</td><td><code>true</code></td></tr><tr><td><code>melodymine.reload</code></td><td>Allows the reloading of all configuration files.</td><td><code>op</code></td></tr><tr><td><code>melodymine.adminmode</code></td><td>Enables listening and speaking with all players in the voice.</td><td><code>op</code></td></tr><tr><td><code>melodymine.mute</code></td><td>Enables muting of players in voice chat.</td><td><code>op</code></td></tr><tr><td><code>melodymine.unmute</code></td><td>Enables unmuting of players in voice chat.</td><td><code>op</code></td></tr><tr><td><code>melodymine.toggle</code></td><td>Toggles voice join and leave message logs.</td><td><code>op</code></td></tr><tr><td><code>melodymine.force</code></td><td>Allows ignoring forced voice joins.</td><td><code>false</code></td></tr><tr><td><code>melodymine.qrcode</code></td><td>Players can use <code>/melodymine start qrcode</code> command.</td><td><code>true</code></td></tr><tr><td><code>melodymine.control</code></td><td>This permission is required for accessing the <code>/melodymine control</code> command and using shortcuts.</td><td><code>true</code></td></tr><tr><td><code>melodymine.call</code></td><td>Player can use <code>/melodymine call</code>.</td><td><code>true</code></td></tr><tr><td></td><td><strong>Children</strong></td><td></td></tr><tr><td></td><td><code>melodymine.call.start</code></td><td></td></tr><tr><td></td><td><code>melodymine.call.end</code></td><td></td></tr><tr><td></td><td><code>melodymine.call.accept</code></td><td></td></tr><tr><td></td><td><code>melodymine.call.deny</code></td><td></td></tr><tr><td></td><td><code>melodymine.call.toggle</code></td><td></td></tr><tr><td><code>melodymine.call.start</code></td><td>Required to start a call.</td><td><code>true</code></td></tr><tr><td><code>melodymine.call.end</code></td><td>Required to end a call.</td><td><code>true</code></td></tr><tr><td><code>melodymine.call.accept</code></td><td>Required to accept a call.</td><td><code>true</code></td></tr><tr><td><code>melodymine.call.deny</code></td><td>Required to deny a call.</td><td><code>true</code></td></tr><tr><td><code>melodymine.call.toggle</code></td><td>Required to toggle call requests.</td><td><code>true</code></td></tr><tr><td><code>melodymine.status</code></td><td>Required for players to use <code>/melodymine status</code> command.</td><td><code>true</code></td></tr><tr><td><code>melodymine.status.others</code></td><td>Required to check other players' voice information.</td><td><code>op</code></td></tr><tr><td><code>melodymine.reset</code></td><td>Required for players to use <code>/melodymine reset</code> command.</td><td><code>op</code></td></tr><tr><td><code>melodymine.updatechecker</code></td><td>get update checker notify.</td><td><code>op</code></td></tr></tbody></table>
