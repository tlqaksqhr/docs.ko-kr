---
title: "&lt;sectionGroup&gt; 요소에 대 한 &lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 654a6e639a24120e1e0c993ebe36f14e75b46a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sectiongroup-element-for-configsections"></a>\<sectionGroup > 요소에 대 한 \<configSections >

구성 섹션에 대 한 네임 스페이스를 정의합니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup >**

## <a name="syntax"></a>구문

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **name**  | 필수 특성입니다.<br><br>정의 하는 섹션 그룹의 이름을 지정 합니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<configSections >** 요소](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | 구성 섹션 및 네임 스페이스 선언을 포함합니다. |

## <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<섹션 >**](~/docs/framework/configure-apps/file-schema/section-element.md) | 구성 섹션 선언을 포함합니다. |

## <a name="remarks"></a>설명

선언 섹션 그룹 구성 섹션에 대 한 컨테이너 태그 만들고 다른 사용자에 의해 정의 된 구성 섹션 이름과 충돌 하지 없는지 확인 합니다. 중첩할 수  **\<sectionGroup >** 요소는 서로 합니다.

## <a name="example"></a>예

다음 예제에는 섹션 그룹에 있는 섹션을 선언 하 고 섹션 그룹을 선언 하는 방법을 보여 줍니다.

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>구성 파일

이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.

## <a name="see-also"></a>참고 항목

[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
