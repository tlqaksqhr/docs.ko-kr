---
title: "Windows Forms 디자이너의 디자인 타임 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DTELErrorList"
  - "WhyDTELPage"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "디자인 타임 오류[Windows Forms Designer]"
  - "오류[Windows Forms Designer]"
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Windows Forms 디자이너의 디자인 타임 오류
이 항목에서는 Windows Forms 디자이너가 로드를 실패했을 때 Microsoft Visual Studio에 나타나는 디자인 타임 오류 목록의 의미와 사용법에 대해 설명합니다.  이 오류 목록이 나타나도 이는 디자이너의 버그가 아니라 단지 코드의 오류를 수정할 수 있도록 돕기 위한 것입니다.  
  
 이 오류 목록을 기본적으로 이해하면 오류에 대한 세부 정보를 제공하고 가능한 해결 방법을 제안하여 응용 프로그램을 손쉽게 디버깅할 수 있습니다.  
  
## 디자인 타임 오류 목록 인터페이스  
 Windows Forms 디자이너가 로드에 실패하면 디자이너에 오류 목록이 나타납니다.  오류는 범주별로 그룹화됩니다.  예를 들어 선언되지 않은 변수의 인스턴스가 네 개 있는 경우 이러한 변수 인스턴스는 동일한 오류 범주로 그룹화됩니다.  각 오류 범주에는 해당 오류를 요약한 간단한 설명이 포함됩니다.  
  
 오류 범주 머리글을 클릭하거나 펼침 단추를 클릭하여 오류 범주를 확장 또는 축소할 수 있습니다.  오류 범주를 확장하면 다음과 같은 추가 도움말이 표시됩니다.  
  
-   이 오류의 인스턴스  
  
-   이 오류에 대한 도움말  
  
-   이 오류에 대한 포럼 게시물  
  
### 이 오류의 인스턴스  
 추가 도움말에는 현재 프로젝트의 모든 오류 인스턴스 목록이 표시됩니다.  대부분의 오류에는 *\[Project Name\]* *\[Form Name\]* Line:*\[Line Number\]* Column:*\[Column Number\]* 형식의 정확한 위치가 포함됩니다.  **코드로 이동** 링크를 클릭하면 코드에서 오류가 발생한 위치로 이동할 수 있습니다.  
  
 호출 스택이 오류와 연결된 경우 **호출 스택 표시** 링크를 클릭하면 오류가 추가로 확장되어 호출 스택이 표시됩니다.  스택을 검사하면 중요한 디버깅 정보를 얻을 수 있습니다.  예를 들어 오류가 발생하기 전에 호출된 기능을 추적할 수 있습니다.  호출 스택은 선택 가능하므로 복사 및 저장할 수 있습니다.  
  
> [!NOTE]
>  Visual Basic에서 디자인 타임 오류 목록에는 둘 이상의 오류가 표시되지 않지만 동일한 오류의 인스턴스가 여러 개 표시될 수는 있습니다.  Visual C\+\+의 오류에는 코드로 이동 링크\/줄 번호 링크가 없습니다.  
  
### 이 오류에 대한 도움말  
 오류에 관련 MSDN 도움말 항목에 대한 링크가 들어 있는 경우 도움말 항목에 대한 링크가 추가 도움말에 포함됩니다.  이 링크를 클릭하면 Visual Studio에 관련 도움말 항목이 나타납니다.  
  
### 이 오류에 대한 포럼 게시물  
 추가 도움말에는 오류와 관련된 MSDN 포럼 게시물에 대한 링크가 포함됩니다.  포럼은 오류 메시지의 문자열을 기반으로 검색됩니다.  다음과 같은 포럼을 검색해 볼 수도 있습니다.  
  
-   [Windows Forms Designer 포럼](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Windows Forms 포럼](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### 무시 후 계속  
 오류 조건을 무시하고 디자이너를 계속 로드하도록 선택할 수 있습니다.  이 동작을 선택하면 예기치 않은 동작이 발생할 수 있습니다.  예를 들어 디자인 화면에 컨트롤이 나타나지 않을 수 있습니다.  
  
## 참고 항목  
 [Troubleshooting Design\-Time Development](../Topic/Troubleshooting%20Design-Time%20Development.md)   
 [컨트롤 및 구성 요소 제작 문제 해결](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)   
 [디자인할 때 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Windows Forms Designer Error Messages](http://msdn.microsoft.com/ko-kr/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)