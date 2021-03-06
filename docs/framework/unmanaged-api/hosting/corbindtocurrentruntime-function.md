---
title: "CorBindToCurrentRuntime Function"
ms.date: "03/30/2017"
api_name: 
  - "CorBindToCurrentRuntime"
api_location: 
  - "mscoree.dll"
  - "mscoreei.dll"
api_type: 
  - "HeaderDef"
f1_keywords: 
  - "CorBindToCurrentRuntime"
helpviewer_keywords: 
  - "CorBindToCurrentRuntime function [.NET Framework hosting]"
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type: 
  - "apiref"
author: "rpetrusha"
ms.author: "ronpet"
---
# CorBindToCurrentRuntime Function
Loads the common language runtime (CLR) into a process by using version information stored in an XML file. The format of the XML file is modeled after the standard application configuration file. For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
 This function has been deprecated in the .NET Framework 4. See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
## Syntax  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## Parameters  
 `pwszFileName`  
 [in] The name of an application configuration file that specifies the version of the CLR to load. If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.  
  
 The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.  
  
 If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.  
  
 `rclsid`  
 [in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface. Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] The `IID` of the interface you are requesting. Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] The returned interface pointer.  
  
## Requirements  
 **Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Library:** MSCorEE.dll  
  
 **.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## See also

- [CorBindToRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost Interface](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
