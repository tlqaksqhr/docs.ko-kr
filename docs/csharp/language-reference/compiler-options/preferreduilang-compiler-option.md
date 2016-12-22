---
title: "/preferreduilang (C# Compiler Options) | Microsoft Docs"
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
  - "/preferreduilang"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "preferreduilang compiler option [C#]"
  - "/preferreduilang compiler option [C#]"
  - "-preferreduilang compiler option [C#]"
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /preferreduilang (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`/preferreduilang` 컴파일러 옵션을 사용하여, C\# 컴파일러 출력에서 오류 메시지 등을 표시 하는 언어를 지정할 수 있습니다.  
  
## 구문  
  
```  
/preferreduilang: language  
```  
  
## 인수  
 `language`  
 컴파일러 출력에 사용할 언어의 [언어 이름](http://go.microsoft.com/fwlink/p/?LinkId=236992) 입니다.  
  
## 설명  
 당신은 `/preferreduilang` 컴파일러 옵션을 C\# 컴파일러 오류 메시지 및 다른 명령줄 출력에 사용할 언어를 지정하기 위해 사용할 수 있습니다.  언어의 언어 팩이 설치 되지 않은 경우, 대신 운영 체제의 언어 설정이 사용되고, 오류가 보고 되지 않습니다.  
  
```c#  
csc.exe /preferreduilang:ja-JP  
```  
  
## 요구 사항  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)