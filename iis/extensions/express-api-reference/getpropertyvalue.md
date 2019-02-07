---
title: "GetPropertyValue | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09c0dfd3-69ad-42b8-87cf-5edd6d9b858b
caps.latest.revision: 8
manager: "wpickett"
---
# GetPropertyValue
Queries the specified property of the IIS version.  
  
## Syntax  
  
```cpp  
    HRESULT  
    GetPropertyValue(  
        [in, string]  BSTR bstrName,  
        [out, retval] VARIANT * pvarValue  
    );  
  
```  
  
#### Parameters  
  
-   [in, string] BSTR `bstrName`  
  
     The name of the property to retrieve (case sensitive). The set of valid property names can be obtained by calling the function with the name `availableReadableProperties` as the `bstrName` parameter, which returns a comma-delimited BSTR. The following are the property names that are valid for all `IIISVersion` objects:  
  
    -   `version`. The version of the product in *major.minor* format.  
  
    -   `productType`. The product type, defined in the [IIS_PRODUCT_TYPE](../../\express-api-reference/iis-product-type.md) enumeration, as a DWORD value (VARIANT I4).  
  
    -   `installPath`. The full path to the install location of the product.  
  
    -   `defaultConfigurationPath`. The default path to the configuration directory. For IIS Express, this path is calculated according the standard location of the user’s configuration directory, which differs by user. The result does not verify the existence of the directory or any files in it.  
  
    -   `defaultSchemaPath`. The default path to the schema file location.  
  
    -   `manifestFile`. The name of the Fusion manifest file for the product. The result can be an empty string if no manifest file exists.  
  
-   [out, retval] VARIANT `* pvarValue`  
  
     The value of the property specified by `bstrName`.  
  
## Return Value  
 `HRESULT`  
  
## Exceptions  
  
## Remarks  
 The following [IIISVersion](../../\express-api-reference/iiisversion.md) objects can be used only for the IIS Express product type:  
  
-   `userInstanceHelper`. An [IIISUserData](../../\express-api-reference/iiisuserdata.md) object.  
  
-   `expressProcessHelper`. An [IIISExpressProcessUtility](../../\express-api-reference/iiisexpressprocessutility.md) object.  
  
## See Also  
 [CreateObjectFromProgId](../../\express-api-reference/createobjectfromprogid.md)   
 [CreateObjectFromCLSID](../../\express-api-reference/createobjectfromclsid.md)   
 [ApplyIISEnvironmentVariables](../../\express-api-reference/applyiisenvironmentvariables.md)   
 [ClearIISEnvironmentVariables](../../\express-api-reference/cleariisenvironmentvariables.md)   
 [ApplyManifestContext](../../\express-api-reference/applymanifestcontext.md)   
 [ClearManifestContext](../../\express-api-reference/clearmanifestcontext.md)