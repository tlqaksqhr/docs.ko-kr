---
title: "리팩터링 및 이름 바꾸기 대화 상자(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RenameSymbol"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "기호, 이름 바꾸기"
  - "이름, 기호 변경"
  - "이름 바꾸기 대화 상자"
ms.assetid: 001d2d81-9bb6-4e8e-ae3a-20c0daaa3959
redirect_url: https://msdn.microsoft.com/library/ckfya594(v=vs.140).aspx
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# 리팩터링 및 이름 바꾸기 대화 상자(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic의 기본 제공 **이름 바꾸기** 대화 상자를 사용하면 코드에서 필드, 지역 변수, 메서드, 네임스페이스, 속성, 형식 등의 기호에 대한 식별자 이름을 바꿀 수 있습니다.  요소 선언을 마우스 오른쪽 단추로 클릭하여 **이름 바꾸기** 대화 상자를 열 수 있습니다.  
  
 **새 이름**  
 코드 요소의 새 이름을 지정합니다.  
  
 **위치**  
 이름 바꾸기 작업을 수행할 때 검색할 네임스페이스를 식별합니다.  
  
## 이름 바꾸기 작업  
 **이름 바꾸기** 대화 상자에서는 이름을 바꾸는 요소의 형식에 따라 서로 조금씩 다른 이름 바꾸기 작업을 수행합니다.  
  
|요소 형식|이름 바꾸기 작업|  
|-----------|---------------|  
|클래스|클래스의 모든 선언과 모든 사용을 새 이름으로 변경합니다.  partial 클래스의 경우 이름 바꾸기 작업이 모든 부분으로 전파됩니다.|  
|필드|필드의 선언과 사용을 새 이름으로 변경합니다.|  
|지역 변수|변수의 선언과 사용을 새 이름으로 변경합니다.|  
|메서드|메서드의 이름과 해당 메서드에 대한 모든 참조를 새 이름으로 변경합니다.|  
|Namespace|네임스페이스의 이름을 새 이름으로 변경하고 선언에 있는 모든 `Imports` 문과 모든 정규화된 이름을 새 이름으로 변경합니다.|  
|Property|속성의 선언과 사용을 새 이름으로 변경합니다.|  
  
## 리팩터링  
 완벽한 리팩터링 기능을 제공하기 위해 Visual Basic은 Developer Express Inc.와 제휴하였습니다.  리팩터링 지원을 얻기 위해.  이 도구를 다운로드하는 방법에 대한 자세한 내용은 MSDN Visual Basic Developer Center에서 [Refactor\!](http://go.microsoft.com/fwlink/?LinkId=155788)를 참조하십시오.  Refactor\!는  15가지 이상의 개별 리팩터링 기능을 지원합니다.  여기에는 매개 변수 다시 정렬, 메서드 추출, 필드 캡슐화 및 오버로드 만들기 같은 작업이 포함됩니다.  
  
## 참고 항목  
 [Using the Visual Basic Development Environment](../../../visual-basic/developing-apps/using-ide/using-the-visual-basic-development-environment.md)