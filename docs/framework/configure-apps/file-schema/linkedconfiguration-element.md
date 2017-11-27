---
title: "&lt;linkedConfiguration&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bfea438ec19303c35ad9d7a2816cb7b9473a00c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration > 요소

포함할 구성 파일을 지정합니다.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration >**

## <a name="syntax"></a>구문

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>특성

|           | 설명 |
| --------- | ----------- |
| **href**  | 필수 특성입니다.<br><br>포함할 구성 파일의 URL입니다. 에 대 한 지원 되는 유일한 형식은 **href** 특성은 `file://`합니다. 로컬 파일과 UNC 파일 지원 됩니다. |

## <a name="parent-element"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<assemblyBinding >** 요소](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | 구성 수준에서 어셈블리 바인딩 정책을 지정합니다. |

## <a name="child-elements"></a>자식 요소

없음

## <a name="remarks"></a>설명

**\<linkedConfiguration >** 요소 구성 요소 어셈블리에 대 한 서비스를 단순화 합니다. 어셈블리를 사용 하는 응용 프로그램의 구성 파일 하나 이상의 응용 프로그램에서 잘 알려진 위치에 있는 구성 파일을 포함 하는 어셈블리를 사용 하는 경우 사용할 수는  **\<linkedConfiguration >** 직접 구성 정보를 포함 하는 것 보다는 어셈블리 구성 파일을 포함 하는 요소입니다. 구성 요소 어셈블리를 서비스를 제공 하는 경우 어셈블리를 사용 하는 모든 응용 프로그램에 업데이트 된 구성 정보를 제공 일반적인 구성 파일을 업데이트 합니다.

> [!NOTE]
> **\<linkedConfiguration >** Windows-side-by-side 매니페스트도 응용 프로그램에 대 한 요소가 지원 되지 않습니다.

연결 된 구성 파일의 사용을 통제 하는 다음 규칙:

- 만 포함 된 구성 파일에서 설정을 로더 바인딩 정책에 영향을 하 게 되 고 로더에 의해서만 사용 됩니다. 포함 된 구성 파일에는 바인딩 정책 이외의 설정이 있을 수 있지만 해당 설정에 영향을 줄 수 없습니다.

- 에 대 한 지원 되는 유일한 형식은 `href` 특성은 `file://`합니다. 로컬 파일과 UNC 파일 지원 됩니다.

- 각 구성 파일에 연결 된 구성 수에 제한이 없습니다.

- 모든 연결 된 구성 파일의 동작과 비슷하지만 한 파일로 병합 됩니다는 `#include` C/c + +에서 지시문입니다.

- **\<linkedConfiguration >** 요소를 응용 프로그램 구성 파일에만 사용할 수 있습니다.;에서 무시 됩니다 *Machine.config*합니다.

- 순환 참조를 감지 하 여 종료 합니다. 즉, 하는 경우는  **\<linkedConfiguration >** 루프를 형성 하는 일련의 구성 파일의 요소, 루프 감지 되 고 중지 합니다.

## <a name="example"></a>예제

다음 예제에는 로컬 하드 디스크에서 구성 파일을 포함 하는 방법을 보여 줍니다.

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>참고 항목

[**\<assemblyBinding >** 요소](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
[.NET Framework에 대 한 구성 파일 스키마](~/docs/framework/configure-apps/file-schema/index.md)
