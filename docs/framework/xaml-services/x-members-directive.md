---
title: "x:Members 지시문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 230c6359c59b9f00738de9ce7ceeccd69899135f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xmembers-directive"></a>x:Members 지시문
부모 요소의 x: 클래스에 적용 되는 태그에 정의 된 멤버 집합을 보유 합니다.  
  
## <a name="xaml-attribute-usage"></a>XAML 특성 사용  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`className`|XAML 프로덕션에 대한 지원 클래스 또는 partial 클래스의 이름입니다. 설명 부분을 참조하세요.|  
|`oneOrMoreMembers`|하나 이상의 개체를 나타내는 요소는 멤버 정의 합니다. 이들은 일반적으로 `x:Property` 개체 요소입니다. 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 .NET Framework XAML 서비스 구현에서 지원 클래스 또는 없을 대 한 기본 멤버 구현이 `x:Members`합니다. `x:Members`모든 형식에 구성원으로 존재할 수 있는 특별 한 XAML 멤버가입니다. XAML 노드 스트림에서 `x:Members` 라는 멤버로 표시 `Members`, XAML 언어 XAML 네임 스페이스에서입니다. 멤버 `Members` 목록이 읽기 전용 제네릭 `Member` 개체입니다. 일반적인 태그 개별 구성원으로 지정 되 `x:Property` 속성 요소입니다. `x:Property`형식의 속성에 대 한 구체적으로 보다 정확 하 게 형식이 며에 할당할 수 `x:Member`합니다. 자세한 내용은 참조 [X:property 지시문](../../../docs/framework/xaml-services/x-property-directive.md)합니다.  
  
 태그로 멤버 정의를 지정하기 위한 수단으로서 `x:Members`의 실제 사용을 지원하려면 멤버가 수정할 수 있는 클래스와 연결되어야 합니다. 의도한 모델은 `x:Members`가 `x:Class`를 지정하는 형식의 멤버로 존재하는 것입니다. 그러나 형식 및 멤버를 연결하거나 동적 멤버 정의를 생성하기 위한 메커니즘은 .NET Framework XAML 서비스 수준에서 지원되지 않습니다. 이 작업은 XAML의 멤버 정의를 지원하는 응용 프로그램 모델이 있는 개별 프레임워크에서 수행해야 합니다. 일반적으로 해당 기능을 지원하려면 XAML을 태그로 컴파일하고 코드 숨김과 통합하거나 XAML 어셈블리에서만 생성하는 MSBUILD 빌드 작업이 필요합니다.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>Windows Workflow Foundation에 대 한 x: 멤버  
 Windows Workflow Foundation에 대 한 `x:Members` XAML 또는 XAML로만 작성 된 사용자 지정 활동의 멤버를 포함 – 코드 숨김 활동 디자이너에 대 한 동적 멤버를 정의 합니다. 또한 XAML 프로덕션의 루트 요소에 `x:Class`를 지정해야 합니다. 이는 .NET Framework XAML 서비스 수준에서의 요구 사항은 아니지만 사용자 지정 활동과 Windows Workflow Foundation XAML을 일반적으로 지원하는 MSBUILD 빌드 작업에 의해 XAML 프로덕션이 로드될 때 요구 사항이 됩니다. `x:Members`첫 번째 자식 요소를 선언 하는 개체 요소의 태그에 있어야는 `x:Class`합니다.
