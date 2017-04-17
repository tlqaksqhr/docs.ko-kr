---
title: "내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "액세스 가능성, Windows Forms 컨트롤 속성"
  - "Windows Forms, 컨트롤의 내게 필요한 옵션 속성"
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성
Windows Forms의 표준 도구 상자에 있는 컨트롤은 키보드 포커스 노출 및 화면 요소 노출을 포함하여 내게 필요한 옵션에 대한 여러 지침을 지원합니다.  
  
## 내게 필요한 옵션에 대한 사전 설계  
 이러한 컨트롤의 속성은 다음 표에서 볼 수 있듯이 내게 필요한 옵션에 대한 다른 지침을 지원하는 데 사용될 수 있습니다.  또한 프로그램 기능에 액세스하려면 메뉴를 사용해야 합니다.  
  
|컨트롤 속성|내게 필요한 옵션에 대한 고려 사항|  
|------------|-------------------------|  
|AccessibleDescription|화면 판독기와 같이 내게 필요한 옵션을 보조하는 도구에 보고되는 설명입니다.  내게 필요한 옵션 보조 도구는 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용할 수 있도록 도와 주는 특수 프로그램 및 장치입니다.|  
|AccessibleName|내게 필요한 옵션을 보조하는 도구에 보고되는 이름입니다.|  
|AccessibleRole|사용자 인터페이스에서 해당 요소의 용도를 설명합니다.|  
|TabIndex|폼을 탐색할 수 있는 기능적인 경로를 만듭니다.  입력란과 같은 내장 레이블이 없는 컨트롤의 경우 탭 순서에서 관련 레이블을 해당 컨트롤 바로 앞에 두는 것이 중요합니다.|  
|Text|선택키를 만들려면 "&" 문자를 사용하십시오.  선택키를 사용하면 문서화된 키보드로 기능에 액세스할 수 있습니다.|  
|글꼴 크기|글꼴 크기를 조정할 수 없는 경우에는 10 포인트 이상으로 설정해야 합니다.  폼의 글꼴 크기를 설정하면 이후에 해당 폼에 추가되는 모든 컨트롤은 같은 글꼴 크기를 갖습니다.|  
|ForeColor|이 속성이 기본값으로 설정되면 폼에서는 사용자의 색 기본 설정이 사용됩니다.|  
|BackColor|이 속성이 기본값으로 설정되면 폼에서는 사용자의 색 기본 설정이 사용됩니다.|  
|BackgroundImage|텍스트를 더 읽기 쉽도록 하려면 이 속성을 비워 두십시오.|  
  
## 참고 항목  
 [연습: 내게 필요한 옵션이 지원되는 Windows 기반 응용 프로그램 만들기](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)