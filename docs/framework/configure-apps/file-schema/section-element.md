---
title: "&lt;섹션&gt; 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8ed8b0211c8366d799fe158d91dcb42f92ad0cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="section-element"></a>\<섹션 > 요소

구성 섹션 선언을 포함합니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션 >**

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션 >**

## <a name="syntax"></a>구문

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a>필수 특성

|           | 설명 |
| --------- | ----------- |
| **name**  | 구성 섹션의 이름을 지정합니다. |
| **type**  | 구성 파일에서 섹션을 읽을 수 있는 구성 섹션 처리기 클래스의 이름을 지정 합니다. 형식 값에 "fully-qualified-section-handler-class-name 단순 어셈블리 이름" 구문이 있습니다. 단순 어셈블리 이름은의 루트 이름 없이 *.dll* 파일 확장명입니다. |

## <a name="optional-attributes"></a>선택적 특성

다음 특성은 ASP.NET 응용 프로그램에만 적용할 수 있습니다. 구성 시스템의 다른 응용 프로그램 종류에 대 한 이러한 특성을 무시합니다.

|                     | 설명 |
| ------------------- | ----------- |
| **allowDefinition** | 섹션에서 사용할 수 있는 구성 파일을 지정 합니다. 다음 값 중 하나를 사용합니다.<br><br>**모든 범위**<br>섹션을을 모든 구성 파일에서 사용할 수 있습니다. 이 값이 기본값입니다.<br>**MachineOnly**<br>섹션을 컴퓨터 구성 파일에만 사용할 수 있습니다 (*Machine.config*).<br>**MachineToApplication**<br>섹션을을 컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에서 사용할 수 있습니다. |
| **allowLocation**   | 섹션 내에서 사용할 수 있는지 여부를 결정 하는  **\<위치 >** 요소입니다. 다음 값 중 하나를 사용합니다.<br><br>**true**<br>섹션 내에서 사용할 수 있습니다는  **\<위치 >** 요소입니다. 이 값이 기본값입니다.<br>**false**<br>섹션 내에서 사용 되도록 허용 하지 않습니다는  **\<위치 >** 요소입니다. |

## <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configSections >** 요소](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 구성 섹션 및 네임 스페이스 선언을 포함합니다. |
| [**\<sectionGroup >** 요소](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | 구성 섹션에 대 한 네임 스페이스를 정의합니다. |

> [!NOTE]
> A  **\<섹션 >** 요소 중 하나의 자식 요소인  **\<configSections >** 또는  **\<sectionGroup >** 하지 않고 둘 다 합니다.

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

구성 파일에 대 한 새 요소를 정의 구성 섹션을 기본적으로 선언 합니다. 새 요소는 구성 섹션 처리기 하는 설정이 포함 되어 (즉, 구현 하는 클래스는 <xref:System.Configuration.IConfigurationSectionHandler> 인터페이스)를 읽습니다. 특성 및 자식 요소 정의 하는 섹션의 설정을 읽는 데 사용 하는 섹션 처리기에 따라 다릅니다.

선언에 구성 섹션 처리기는 *Machine.config* 파일을 사용 하면 해당 컴퓨터에서 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있는 경우가 아니면는 **allowDefinition**특성 그렇지 않도록 지정 합니다.

## <a name="example"></a>예제

다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고 항목

[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
