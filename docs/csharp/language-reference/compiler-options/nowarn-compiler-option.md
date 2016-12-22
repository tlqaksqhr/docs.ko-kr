---
title: "/nowarn (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/nowarn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowarn compiler option [C#]"
  - "/nowarn compiler option [C#]"
  - "-nowarn compiler option [C#]"
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /nowarn (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/nowarn** 옵션을 사용하면 컴파일러에서 경고를 하나 이상 표시하지 않도록 할 수 있습니다.  각 경고 번호는 쉼표로 구분합니다.  
  
## 구문  
  
```  
/nowarn:number1[,number2,...]  
```  
  
## 인수  
 `number1`, `number2`  
 컴파일러에서 표시하지 않으려는 경고 번호입니다.  
  
## 설명  
 경고 식별자의 숫자 부분만 지정해야 합니다.  예를 들어, CS0028을 표시하지 않으려면 `/nowarn:28`을 지정합니다.  
  
 이전 릴리스에서는 유효하지만 현재는 제거된 경고 번호가 `/nowarn`에 전달되면 컴파일러에서는 이를 무시합니다.  예를 들어, CS0679는 Visual Studio .NET 2002의 컴파일러에서는 유효하지만 이후 릴리스에서는 제거되었습니다.  
  
 다음 경고는 `/nowarn` 옵션으로 표시되지 않도록 설정할 수 없습니다.  
  
-   Compiler Warning \(level 1\) CS2002  
  
-   Compiler Warning \(level 1\) CS2023  
  
-   Compiler Warning \(level 1\) CS2029  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  자세한 내용은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp)를 참조하십시오.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **경고 표시 안 함** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>을 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)