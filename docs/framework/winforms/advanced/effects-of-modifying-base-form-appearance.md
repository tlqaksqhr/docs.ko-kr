---
title: "기본 폼의 모양 수정 효과 | Microsoft Docs"
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
  - "기본 폼"
  - "상속, 폼"
  - "상속된 폼, 기본으로 수정"
  - "부모 폼"
  - "Windows Forms, 기본 폼 모양"
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 기본 폼의 모양 수정 효과
응용 프로그램 개발 과정에서 해당 프로젝트 또는 기타 프로젝트의 다른 폼들에 상속되는 기본 폼의 모양을 변경해야 하는 경우가 종종 있습니다.  
  
 디자인 타임에 속성 설정 또는 컨트롤 추가 및 제거를 통해 수행한 기본 폼의 모양 변경 내용은 기본 폼을 포함하는 프로젝트를 빌드할 때 상속된 폼에 반영됩니다.  기본 폼의 변경 내용을 저장하는 것만으로는 변경 내용이 반영되지 않습니다.  프로젝트를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
 런타임에 수행한 기본 폼의 수정 내용은 이미 인스턴스화된 상속된 폼에 아무런 영향을 미치지 않습니다.  
  
## 참고 항목  
 [base](../Topic/base%20\(C%23%20Reference\).md)   
 [방법: Windows Forms 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Windows Forms 시각적 상속](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)