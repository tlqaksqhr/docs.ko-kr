---
title: "Lambda Expressions in PLINQ and TPL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Func delegate, creating with lambda expression"
  - "Action delegate, creating with lambda expression"
  - "lambda expressions, with Action and Func"
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Lambda Expressions in PLINQ and TPL
TPL\(작업 병렬 라이브러리\)에는 입력 매개 변수로 대리자의 <xref:System.Func%601?displayProperty=fullName> 또는 <xref:System.Action?displayProperty=fullName> 패밀리 중 하나를 사용하는 여러 메서드가 들어 있습니다.  이러한 대리자를 사용하여 병렬 루프, 작업 또는 쿼리에 사용자 지정 프로그램 논리를 전달합니다.  TPL과 PLINQ를 위한 코드 예제에서는 람다 식을 사용하여 이러한 대리자의 인스턴스를 인라인 코드 블록으로 만듭니다.  이 항목에서는 Func 및 Action에 대해 간략히 소개하고 작업 병렬 라이브러리 및 PLINQ에서 람다 식을 사용하는 방법을 보여 줍니다.  
  
 **참고** 일반적인 대리자에 대한 자세한 내용은 [대리자](../Topic/Delegates%20\(C%23%20Programming%20Guide\).md) 및 [Delegates](../Topic/Delegates%20\(Visual%20Basic\).md)를 참조하십시오.  C\# 및 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 람다 식에 대한 자세한 내용은 [람다 식](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md) 및 [Lambda Expressions](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md)을 참조하십시오.  
  
## Func 대리자  
 `Func` 대리자는 값을 반환하는 메서드를 캡슐화합니다.  Func 시그니처에서 마지막 또는 맨 오른쪽의 형식 매개 변수는 항상 반환 형식을 지정합니다.  컴파일러 오류가 발생하는 일반적인 원인 중 하나는 사실 <xref:System.Func%602?displayProperty=fullName>는 하나의 입력 매개 변수만 사용하는데 여기에 두 개의 입력 매개 변수를 전달하려고 하기 때문입니다.  .NET Framework 클래스 라이브러리에는 17개 버전의 `Func`, 즉 <xref:System.Func%601?displayProperty=fullName>, <xref:System.Func%602?displayProperty=fullName>, <xref:System.Func%603?displayProperty=fullName>부터 <xref:System.Func%6017?displayProperty=fullName>까지의 버전이 정의되어 있습니다.  
  
## Action 대리자  
 <xref:System.Action?displayProperty=fullName> 대리자는 값을 반환하지 않거나 [void](../Topic/void%20\(C%23%20Reference\).md)를 반환하는 메서드\([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 Sub\)를 캡슐화합니다.  Action 형식의 시그니처에서 형식 매개 변수는 입력 매개 변수만을 나타냅니다.  Func의 경우와 마찬가지로 .NET Framework 클래스 라이브러리에는 형식 매개 변수가 없는 버전부터 16개의 형식 매개 변수가 있는 버전까지 모두 17개 버전의 Action이 정의되어 있습니다.  
  
## 예제  
 <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=fullName> 메서드에 대한 다음 예제에서는 람다 식을 사용하여 Func 및 Action 대리자를 표현하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## 참고 항목  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)