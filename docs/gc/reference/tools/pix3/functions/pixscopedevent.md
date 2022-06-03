---
author: aablackm
title: PIXScopedEvent(UINT64, PCSTR, ...)
description: Creates a user-defined event for a timing capture of CPU activity, to be displayed in the **Timing Capture** feature of Performance Investigator for Xbox (PIX).
kindex:
- PIXScopedEvent
- PIX, PIXScopedEvent
ms.author: jerry.zhou
ms.topic: reference
edited: 10/16/2020
quality: good
security: public
---

# PIXScopedEvent
  
Creates a user-defined event for a timing capture of CPU activity, to be displayed in the **Timing Capture** feature of Performance Investigator for Xbox (PIX).  
  
<a id="syntaxSection"></a>
  
## Syntax
  
```cpp
void PIXScopedEvent(
         UINT64 color,
         _In_ PCSTR formatString,
         ...
)
```  
  
<a id="parametersSection"></a>
  
### Parameters
  
*color* &nbsp;&nbsp;  
Type: UINT64  
  
The event color to use in the timeline chart. Specify a [PIX_COLOR](pix_color.md) constant to use a pre-defined color, a [PIX_COLOR_INDEX](pix_color_index.md) constant to use a color index, or a DWORD value in ARGB format to use a custom color. If an ARGB-formatted DWORD value is specified, the alpha channel for that value must be set to `0xff`.  
  
*formatString* &nbsp;&nbsp;\_In\_  
Type: PCWSTR  
  
The name to use to describe the event, as a pointer to a null-terminated Unicode string. The string may specify zero or more optional string format placeholders, very similar to `sprintf` formatting. This method supports up to 16 placeholders.  
  
Type: ...  
  
If placeholders are specified in *formatString*, you must specify a corresponding number of values in this parameter. The types of the values specified in this parameter depend on the types identified by their corresponding placeholders.  
  
<a id="retvalSection"></a>
  
### Return value
  
Type: void  
  
None.  
  
<a id="remarksSection"></a>
  
## Remarks
  
This function creates a user-defined event for a timing capture of CPU activity, to be displayed in the **Timing Capture** feature of PIX. Events created with `PIXScopedEvent` automatically end when the scope the API is called in is exited, thus making the matching of the event’s start and its end automatic.  
  
The `PIXScopedEvent` function saves the format string and format parameters instead of formatting the string at runtime. Formatting is then done when reading capture files in PIX. Use 8-byte aligned strings or, preferably, 16-byte aligned strings with `PIXScopedEvent` to get the best performance. To format a `char\*` or `wchar_t\*` as a pointer using the `%p` format specifier, cast the pointer to either a `void\*` or to any integral or floating point type when passing the pointer to `PIXScopedEvent`.  
  
Calls to `PIXScopedEvent` are guaranteed at least 512 bytes of space to save the record data, which includes the full size and alignment of the format string and all variables. In general, PIX events are intended for short high-performance markers that align to your game’s major components, systems, or content.  
  
<a id="requirementsSection"></a>
  
## Requirements
  
**Header:** pix3.h  
  
**Library:** pixevt.lib  
  
**Supported platforms:** Xbox One family consoles and Xbox Series consoles  
  
<a id="seealsoSection"></a>
  
## See also
  
[PIXScopedEvent](pixscopedevent-overloads.md)  
[PIX3](../pix3_members.md)  
[PIX (NDA topic)](../../../../tools-console/xbox-tools-and-apis/pix/pix.md)  
  