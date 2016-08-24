# Flagging on the @status attribute

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

NOTE: There is a bug in OT 2.2.4 that causes the flagging on @status values to not
work (symptom is an XSLT error about incorrect return types in the flagging preprocessing
part of the OT log). This bug is fixed in OT 2.2.5.

## Open Toolkit Versions Supported

While the enabling of @status flagging works with the 1.8.5 and later versions of the
OT, the ability to actually flag on @status values may work in 1.8.5 but will not work
in the 2.x OT before 2.2.5 due to bugs in the flagging preprocessing added in OT 2.x.

This plugin works by adding "a(props status)" to the @domains value for every map and
topic. This has the effect of making the flagging and filtering processors think that @status is
a specialization of @props and thus something you can filter on or flag using normal
DITAVAL files. While making this change to @domains is, technically, a lie, because @status
is not a specialization of @props and is not defined in the DITA spec as an attribute that
MUST allow filtering and flagging, it doesn't hurt anything because there is no processing
other than filtering and flagging that cares about the @domains value.

A more complete solution would be for the OT to provide more general extension points
for enabling filtering and flagging on attributes other than those defined in the DITA 
specification. Those extensions are planned for OT 2.3.  
