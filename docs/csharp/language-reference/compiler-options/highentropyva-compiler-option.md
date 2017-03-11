---
title: "/highentropyva (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/highentropyva"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/highentropyva compiler option [C#]"
  - "-highentropyva compiler option [C#]"
  - "highentropyva compiler option [C#]"
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# /highentropyva (C# Compiler Options)
**\/highentropyva** 컴파일러 옵션은 Windows 커널이 특정 실행 파일이 높은 엔트로피 주소 공간 레이아웃 불규칙화 \(ASLR\)를 지원 하는지 여부를 알려 줍니다.  
  
## 구문  
  
```  
/highentropyva[+ | -]  
```  
  
## 인수  
 `+` &#124; `-`  
 이 옵션은 64 비트 실행 파일 또는 높은 엔트로피 가상 주소 공간을 지원  [\/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) 컴파일러 옵션에 의해 표시 되는 실행 파일을 지정 합니다.  기본적으로 이 옵션은 사용불가 합니다.  **\/highentropyva\+** 또는 **\/highentropyva** 를 사용하여 활성화 합니다.  
  
## 설명  
 **\/highentropyva** 옵션은 Windows 커널의 호환 되는 버전이 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 불규칙화 할 때 더 높은 수준으로 엔트로피를 사용하도록 가능하게 합니다.  더 높은 수준으로 엔트로피를 사용하는 것은 스택 및 힙 메모리 영역에 더 많은 주소를 할당할 수 있음을 의미 합니다.  따라서, 특정 메모리 영역의 위치를 추측 하기 어렵게 됩니다.  
  
 **\/highentropyva** 컴파일러 옵션을 지정한 경우, 대상 실행 파일 및 의존 하는 모든 모듈은 64 비트 프로세스로 실행 하는 경우 4GB \(기가바이트\) 보다 큰 포인터 값을 처리할 수 있어야 합니다.  
  
 ASLR에 대한 자세한 내용은 다음을 참조하십시오. [Mitigating Software Vulnerabilities](http://go.microsoft.com/fwlink/?LinkId=226234).