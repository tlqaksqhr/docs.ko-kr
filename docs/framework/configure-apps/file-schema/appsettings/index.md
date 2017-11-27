---
title: "앱 설정 스키마"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d51d06895e61be60bbe9153eacb2028cb32a1fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="app-settings-schema"></a>앱 설정 스키마

파일 경로, XML Web services URL 또는 응용 프로그램의 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 설정이 포함되어 있습니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md)

| 요소 | 설명 |
| ------- | ----------- |
| [**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | 응용 프로그램 설정을 제어하기 위한 **\<add>**, **\<clear>** 및 **\<remove>** 태그가 포함되어 있습니다. 선택적 **파일** 특성이 있습니다. |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | 설정을 정의합니다. **\<appSettings>**의 자식 요소입니다. **키** 및 **값** 특성이 필요합니다. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | 모든 설정을 지웁니다. **\<appSettings>**의 자식 요소입니다. 특성이 없습니다. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | 설정을 제거합니다. **\<appSettings>**의 자식 요소입니다. **키** 특성이 필요합니다. |

## <a name="appsettings-element"></a>\<appSettings> 요소

이 요소에는 응용 프로그램 설정을 제어하기 위한 **\<add>**, **\<clear>** 및 **\<remove>** 태그가 포함되어 있습니다. **파일**에 대한 선택적 특성을 정의합니다.

## <a name="add-element"></a>\<add> 요소

응용 프로그램 설정 컬렉션에 사용자 지정 응용 프로그램 설정을 이름/값 쌍으로 추가합니다. **키** 및 **값**에 대한 특성을 정의합니다.

## <a name="clear-element"></a>\<clear> 요소

상속된 사용자 지정 응용 프로그램 설정에 대한 참조를 모두 제거하고, **\<clear>** 요소 다음의 **\<add>** 요소에 의해 추가된 참조만 허용합니다. 특성 없음을 정의합니다.

## <a name="remove-element"></a>\<remove> 요소

상속된 사용자 지정 응용 프로그램 설정에 대한 참조를 응용 프로그램 설정 컬렉션에서 제거합니다. **키**에 대한 특성을 정의합니다.

## <a name="example"></a>예제

다음 예제에서는 사용자 지정 응용 프로그램 설정을 정의하는 외부 응용 프로그램 설정 파일(*custom.config*)을 보여 줍니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 응용 프로그램 설정을 지정하는 응용 프로그램 구성 파일을 보여 줍니다.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a>참고 항목

[응용 프로그램 설정 개요](~/docs/framework/winforms/advanced/application-settings-overview.md)   
[응용 프로그램 설정 아키텍처](~/docs/framework/winforms/advanced/application-settings-architecture.md)
