---
title: "Derived Math Functions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arithmetic operations, derived math functions"
  - "cosecant function"
  - "arcsecant function"
  - "arccotangent function"
  - "functions [Visual Basic], derived math functions"
  - "inverse functions"
  - "math functions, derived"
  - "derived math functions"
  - "cotangent function"
  - "angles"
  - "secant function"
  - "trigonometric functions"
  - "logarithms"
  - "arccosecant function"
  - "hyperbolic functions"
  - "arcsine function"
  - "degrees"
  - "arccosine function"
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Derived Math Functions (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음 표에서는 <xref:System.Math?displayProperty=fullName> 개체의 내장 수학 함수에서 파생될 수 있는 비내장 수학 함수를 보여 줍니다.  이 내장 수학 함수는 파일 또는 프로젝트에 `Imports System.Math`를 추가하여 액세스할 수 있습니다.  
  
|Function|파생된 비내장 함수|  
|--------------|----------------|  
|시컨트\(Sec\(x\)\)|1 \/ Cos\(x\)|  
|코시컨트\(Csc\(x\)\)|1 \/ Sin\(x\)|  
|코탄젠트\(Ctan\(x\)\)|1 \/ Tan\(x\)|  
|역 사인\(Asin\(x\)\)|Atan\(x \/ Sqrt\(\-x \* x \+ 1\)\)|  
|역 코사인\(Acos\(x\)\)|Atan\(\-x \/ Sqrt\(\-x \* x \+ 1\)\) \+ 2 \* Atan\(1\)|  
|역 시컨트\(Asec\(x\)\)|2 \* Atan\(1\) – Atan\(Sign\(x\) \/ Sqrt\(x \* x – 1\)\)|  
|역 코시컨트\(Acsc\(x\)\)|Atan\(Sign\(x\) \/ Sqrt\(x \* x – 1\)\)|  
|역 코탄젠트\(Acot\(x\)\)|2 \* Atan\(1\) \- Atan\(x\)|  
|하이퍼볼릭 사인\(Sinh\(x\)\)|\(Exp\(x\) – Exp\(\-x\)\) \/ 2|  
|하이퍼볼릭 코사인\(Cosh\(x\)\)|\(Exp\(x\) \+ Exp\(\-x\)\) \/ 2|  
|하이퍼볼릭 탄젠트\(Tanh\(x\)\)|\(Exp\(x\) – Exp\(\-x\)\) \/ \(Exp\(x\) \+ Exp\(\-x\)\)|  
|하이퍼볼릭 시컨트\(Sech\(x\)\)|2 \/ \(Exp\(x\) \+ Exp\(\-x\)\)|  
|하이퍼볼릭 코시컨트\(Csch\(x\)\)|2 \/ \(Exp\(x\) – Exp\(\-x\)\)|  
|하이퍼볼릭 코탄젠트\(Coth\(x\)\)|\(Exp\(x\) \+ Exp\(\-x\)\) \/ \(Exp\(x\) – Exp\(\-x\)\)|  
|역 하이퍼볼릭 사인\(Asinh\(x\)\)|Log\(x \+ Sqrt\(x \* x \+ 1\)\)|  
|역 하이퍼볼릭 코사인\(Acosh\(x\)\)|Log\(x \+ Sqrt\(x \* x – 1\)\)|  
|역 하이퍼볼릭 탄젠트\(Atanh\(x\)\)|Log\(\(1 \+ x\) \/ \(1 – x\)\) \/ 2|  
|역 하이퍼볼릭 시컨트\(AsecH\(x\)\)|Log\(\(Sqrt\(\-x \* x \+ 1\) \+ 1\) \/ x\)|  
|역 하이퍼볼릭 코시컨트\(Acsch\(x\)\)|Log\(\(Sign\(x\) \* Sqrt\(x \* x \+ 1\) \+ 1\) \/ x\)|  
|역 하이퍼볼릭 코탄젠트\(Acoth\(x\)\)|Log\(\(x \+ 1\) \/ \(x – 1\)\) \/ 2|  
  
## 참고 항목  
 [수학 함수](../../../visual-basic/language-reference/functions/math-functions.md)