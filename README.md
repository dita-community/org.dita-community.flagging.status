# FLagging on the @status attribute

Enables flagging on the @status attribute value using normal ditaval mechanisms

With this plugin installed you can use DITAVAL files to flag @status values
just as you would any other conditional attribute.

For example, to produce the usual blue/green/red for new/changed/deleted values
you can do:
{code}
<prop action="flag" att="status" val="new" color="blue" style="overline"/>
<prop action="flag" att="status" val="changed" color="green"/>
<prop action="flag" att="status" val="deleted" color="red" style="line-through"/>
{code}

Note that the value "line-through" for @style is not supported in HTML by the base
Open Toolkit. This plugin extends the 2.2.5+ HTML flagging code to implement
the line-through style.

## Open Toolkit Version Supported

For general enabling of @status flagging, this plugin works with the 1.8.5 and
2.x Open Toolkit versions.

The HTML flagging extension to support line-through only works with OT 2.2.5 and
newer. 