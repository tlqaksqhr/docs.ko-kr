---
title: "/recurse (C# Compiler Options) | Microsoft Docs"
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
  - "/recurse"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/recurse compiler option [C#]"
  - "recurse compiler option [C#]"
  - "-recurse compiler option [C#]"
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /recurse (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\/recurse 옵션을 사용하면 지정된 디렉터리\(dir\) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일이 컴파일됩니다.  
  
## 구문  
  
```  
/recurse:[dir\]file  
```  
  
## 인수  
 `dir`\(선택적 요소\)  
 검색을 시작할 디렉터리입니다.  이 옵션을 지정하지 않으면 프로젝트 디렉터리에서 검색을 시작합니다.  
  
 `file`  
 검색할 파일입니다.  와일드카드 문자를 사용할 수 있습니다.  
  
## 설명  
 **\/recurse** 옵션을 사용하면 디렉터리\(`dir`\) 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일이 컴파일됩니다.  
  
 **\/recurse**를 사용하지 않고 파일 이름에 와일드카드를 사용하여 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다.  
  
 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.  
  
## 예제  
 현재 디렉터리에 있는 모든 C\# 파일을 컴파일합니다.  
  
```  
csc *.cs  
```  
  
 dir1\\dir2 디렉터리와 이 디렉터리의 모든 하위 디렉터리에 있는 모든 C\# 파일을 컴파일하여 dir2.dll을 만듭니다.  
  
```  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)