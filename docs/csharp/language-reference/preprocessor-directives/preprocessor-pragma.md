---
title: "#pragma(C# 참조) | Microsoft Docs"
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
  - "#pragma"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma 지시문[C#]"
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #pragma(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#pragma`는 컴파일러에 이 지시문이 포함된 파일을 컴파일하기 위한 특수 명령을 제공합니다.  컴파일러가 해당 명령을 지원해야 합니다.  즉, `#pragma`를 사용하여 사용자 지정 전처리 명령을 만들 수 없습니다.  Microsoft C\# 컴파일러는 다음과 같은 두 개의 `#pragma` 명령을 지원합니다.  
  
 [\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [\#pragma checksum](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## 구문  
  
```  
#pragma pragma-name pragma-arguments  
```  
  
#### 매개 변수  
 `pragma-name`  
 인식할 수 있는 pragma 이름입니다.  
  
 `pragma-arguments`  
 pragma 관련 인수입니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)   
 [\#pragma checksum](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)