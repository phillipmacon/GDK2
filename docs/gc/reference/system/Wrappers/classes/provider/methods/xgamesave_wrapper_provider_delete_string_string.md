---
author: M-Stahl
title: Delete(std::string&, std::string&)
description: Deletes the specified blobs (files) from the specified container.
kindex: Wrappers.XGameSave.Provider.Delete(std::string&, std::string&)
ms.author: jgup
ms.topic: reference
ms.date: 02/23/2020
edited: 02/02/2021
security: public
applies-to: pc-gdk
---

# Microsoft.Xbox.Wrappers.XGameSave.Provider.Delete(std::string&, std::string&)

Deletes the specified blobs (files) from the specified container.

<a id="syntaxSection"></a>

## Syntax

```cpp
HRESULT Delete(const std::string& containerName,
               const std::string& blobName);
```

<a id="parametersSection"></a>

### Parameters

*containerName*&nbsp;&nbsp; \_In\_  
Type: std::string

The name of the container.

*blobName*&nbsp;&nbsp;\_In\_  
Type: std::string

The name of the blob to delete.

<a id="retvalSection"></a>

### Return value

Type: HRESULT

This method returns **S_OK** upon success, or an error code otherwise.

<a id="remarksSection"></a>

## Remarks

You must call the [Initialize](xgamesave_wrapper_provider_initialize.md) method before you can call any other method from the `Provider` class.

To delete one or more blobs from the specified container, call [Delete(std::string&, BlobNames&)](xgamesave_wrapper_provider_delete_string_blobnames.md).

To delete a container along with all of its blobs, call [Delete(std::string&)](xgamesave_wrapper_provider_delete_string.md).

<a id="requirementsSection"></a>

## Requirements

**Header:** xgamesavewrappers.hpp
  
**Supported platforms:** Windows, Xbox One family consoles and Xbox Series consoles

<a id="seealsoSection"></a>

## See also

[Microsoft.Xbox.Wrappers.XGameSave.Provider](../xgamesave_wrapper_provider.md)  
[XGameSave wrapper members](../../../xgamesave_wrapper_members.md)  
[Game saves simplified wrapper](../../../../../../system/overviews/game-save/game-saves-simplified-wrapper.md)  