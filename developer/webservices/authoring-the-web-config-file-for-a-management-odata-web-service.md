---
title: 관리 OData 웹 서비스에 대 한 Web.config 파일을 작성 | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569f5d5-9746-40c0-be5e-f218bc4560f7
caps.latest.revision: 4
ms.openlocfilehash: f52953ee091f05df5f355719ecba788d3d5ee055
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856719"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a>관리 OData 웹 서비스용 Web.config 파일 작성

관리 OData 웹 서비스를 배포할 수 있습니다, web.config 파일을 구현 하는 Dll 및 XML 스키마 파일을 가리키도록 구성 해야 합니다는 [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) 고 [ System.Management.Automation.Remoting.Pssessionconfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration) 인터페이스입니다.

## <a name="sample-config-file"></a>샘플 구성 파일

다음은 웹 서비스에 대 한 web.config 파일의 모양은의 예입니다.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
   <configSections>
      <section name="managementOdata" type="Microsoft.Management.Odata.Core.DSConfiguration, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL" />
   </configSections>
   <managementOdata schemaFileName="Schema.mof" resourceMappingFileName="Schema.xml">
      <customAuthorization type="Microsoft.Samples.Management.OData.RoleBasedPlugins.CustomAuthorization" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      <powershell>
         <sessionConfiguration type="Microsoft.Samples.Management.OData.RoleBasedPlugins.SessionConfiguration" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      </powershell>
      <commandInvocation enabled="true" />
      <wcfDataServicesConfig>
      </wcfDataServicesConfig>
   </managementOdata>
   <system.serviceModel>
      <behaviors>
         <serviceBehaviors>
            <behavior>
                  <serviceAuthorization serviceAuthorizationManagerType="Microsoft.Management.Odata.Core.CustomAuthorizationManager, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
            </behavior>
         </serviceBehaviors>
      </behaviors>
      <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
   </system.serviceModel>
   <system.webServer>
      <security>
         <authentication>
            <anonymousAuthentication enabled="false" />
            <basicAuthentication enabled="true" />
            <windowsAuthentication enabled="false" />
         </authentication>
      </security>
  </system.webServer>
</configuration>

```

## <a name="see-also"></a>참고 항목

[관리 OData 웹 서비스에 대 한 사용자 지정 권한 부여를 구현합니다.](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[관리 OData 웹 서비스에 대 한 SessionConfiguration 구현](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[관리 OData 웹 서비스의 MOF 스키마 파일 작성](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[관리 OData 웹 서비스에 대 한 XML 스키마 파일 작성](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[관리 OData 웹 서비스 만들기](./creating-a-management-odata-web-service.md)