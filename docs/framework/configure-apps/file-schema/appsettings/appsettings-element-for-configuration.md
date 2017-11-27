---
title: "&lt;appSettings&gt; 요소에 대 한 &lt;구성&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cb59120d88816ea193bd8588b152d6b848b682d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="appsettings-element-for-configuration"></a>\<g s > 요소에 대 한 \<구성 >

사용자 지정 응용 프로그램 설정을 포함합니다. .NET Framework에서 제공 하는 미리 정의 된 구성 섹션입니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<g s >**

## <a name="syntax"></a>구문

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **file**  | 선택적 특성입니다.<br><br>사용자 지정 응용 프로그램 구성 설정이 포함 된 외부 파일의 상대 경로 지정 합니다. 지정한 파일에 지정 된 설정의 같은 종류에는  **\<추가 >**,  **\<제거 >**, 및  **\<지우기 >** 요소와 해당 요소와 동일한 키/값 쌍이 형식을 사용 합니다.<br><br>지정 된 경로가 기본 구성 파일을 기준으로 합니다. 이것은 이진 폴더는 Windows Forms 응용 프로그램에 대 한 (같은 */bin/debug*), 응용 프로그램 구성 파일의 위치에 없습니다. Web Forms 응용 프로그램에 대 한 응용 프로그램 루트에 상대적인 경로 여기서는 *web.config* 파일은 합니다.<br><br>Note 지정된 된 파일을 찾을 수 없는 경우 런타임은 특성을 무시 합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<구성 >** 요소](~/docs/framework/configure-apps/file-schema/configuration-element.md) | 공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다. |

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<add>**](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | 사용자 지정 응용 프로그램 설정을 추가합니다. |
| [**\<clear>**](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | 모든 이전에 정의 된 응용 프로그램 설정을 지웁니다. |
| [**\<remove>**](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | 이전에 정의 된 응용 프로그램 설정을 제거합니다. |

## <a name="remarks"></a>설명

**\<g s >** 데이터베이스 연결 문자열, 파일 경로, XML 웹 서비스 Url에 대 한 사용자 지정 구성 정보 등의 사용자 지정 응용 프로그램 구성 정보를 저장 하는 요소는 응용 프로그램입니다. 에 지정 된 키/값 쌍의  **\<appSettings >** 요소가 사용 하 여 코드에 액세스 하는 <xref:System.Configuration.ConfigurationSettings> 클래스입니다.

사용할 수는 **파일** 특성에  **\<g s >** 의 요소는 *Web.config* 및 응용 프로그램 구성 파일입니다. 추가 설정을 제공 하거나에 지정 된 설정을 재정의 하는 구성 파일을 지정 하는이 특성은  **\<g s >** 요소입니다. **파일** 특성은 사용자가 응용 프로그램 구성 파일에 지정 된 프로젝트 설정을 재정의 하려는 경우 처럼 소스 제어 팀 개발 시나리오에서 사용할 수 있습니다.

지정 된 구성 파일의 **파일** 특성의 루트 노드에 있어야 합니다.  **\<g s >** 대신  **\<구성 >**.

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

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고 항목

[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
