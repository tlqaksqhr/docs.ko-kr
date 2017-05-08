---
title: "사용자 지정 활동 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 사용자 지정 활동 사용
<xref:System.Activities.Activity> 또는 해당 하위 클래스에서 파생되는 활동은 더 큰 워크플로로 구성하거나 코드로 직접 작성할 수 있습니다.이 항목에서는 코드나 디자이너에서 만든 워크플로에서 사용자 지정 활동을 사용하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  사용자 지정 활동과 해당 사용자 지정 활동을 사용하는 활동이 모두 컴파일된 경우\(즉, 빌드 프로세스에서 생성된 인스턴스화 형식에 의해 로드된 경우\) 사용자 지정활동을 해당 활동이 정의된 것과 프로젝트에서 사용할 수 있습니다. 참조하는 활동이 동적으로 로드된 경우\(즉,ActivityXAMLServices를 사용하는 경우\)에는 참조되는 어셈블리를 다른 프로젝트에 배치하거나 디자이너에서 생성된 XAML을 편집하여 해당 어셈블리를 사용할 수 있도록 해야 합니다.  
  
#### 워크플로 프로젝트에 사용자 지정 활동 사용  
  
1.  사용자 지정 활동이 포함된 활동 라이브러리 프로젝트에 호스트 프로젝트에서의 참조를 추가합니다.  
  
2.  솔루션을 빌드합니다.  
  
3.  디자이너에서 사용자 지정 활동을 사용하려면 도구 상자에서 사용자 지정 활동을 찾아 디자이너 화면으로 끌어 옵니다.  
  
4.  코드에서 사용자 지정 활동을 사용하려면 사용자 지정 활동 프로젝트를 참조하는 Using 문을 추가하고 활동의 새 인스턴스를 <xref:System.Activities.WorkflowInvoker.Invoke%2A>에 전달합니다.