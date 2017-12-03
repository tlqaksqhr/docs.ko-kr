---
title: "사용자 지정 활동 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cea0e819c79550b27a71957f6d8c2c9badfef7c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-a-custom-activity"></a>사용자 지정 활동 사용
<xref:System.Activities.Activity> 또는 해당 하위 클래스에서 파생되는 활동은 더 큰 워크플로로 구성하거나 코드로 직접 작성할 수 있습니다. 이 항목에서는 코드나 디자이너에서 만든 워크플로에서 사용자 지정 활동을 사용하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  사용자 지정 활동 정의 된 동일한 프로젝트에 사용할 수는 사용자 지정 활동과 활동을 사용 하 여 (즉, 빌드 프로세스에 의해 생성 된 인스턴스화하는 동안 유형 로드) 컴파일된으로 참조 하는 활동은 로드 된 경우 동적으로 참조 된 어셈블리를 다른 프로젝트에 배치 해야 합니다 (예:: ActivityXAMLServices 사용) 또는 디자이너에서 생성 된 XAML이 방법을 사용 하려면 직접 편집한 되도록 해야 합니다.  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>워크플로 프로젝트에 사용자 지정 활동 사용  
  
1.  사용자 지정 활동이 포함된 활동 라이브러리 프로젝트에 호스트 프로젝트에서의 참조를 추가합니다.  
  
2.  솔루션을 빌드합니다.  
  
3.  디자이너에서 사용자 지정 활동을 사용하려면 도구 상자에서 사용자 지정 활동을 찾아 디자이너 화면으로 끌어 옵니다.  
  
4.  코드에서 사용자 지정 활동을 사용하려면 사용자 지정 활동 프로젝트를 참조하는 Using 문을 추가하고 활동의 새 인스턴스를 <xref:System.Activities.WorkflowInvoker.Invoke%2A>에 전달합니다.
