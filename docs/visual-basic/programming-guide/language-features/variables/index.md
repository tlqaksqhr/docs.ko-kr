---
title: "Variables in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic]"
  - "values [Visual Basic], storing"
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Variables in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 계산을 수행하는 경우 값을 자주 저장해야 합니다.  예를 들어, 여러 개의 값을 계산하고 비교한 다음 해당 결과에 따라 여러 가지 작업을 수행해야 하는 경우가 있을 수 있습니다.  값을 비교하려면 해당 값을 유지해야 합니다.  
  
## 용도  
 대부분의 프로그래밍 언어와 마찬가지로 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서도 변수를 사용하여 값을 저장합니다.  *변수*는 해당 변수에 저장된 값을 참조하는 데 사용하는 이름과  해당 변수에 저장될 수 있는 데이터의 종류를 결정하는 데이터 형식을 가집니다.  밀접하게 관련되어 있으며 인덱싱된 데이터 항목 집합을 저장해야 하는 경우 변수에 배열을 사용할 수 있습니다.  
  
 지역 형식 유추를 사용하면 데이터 형식을 명시적으로 지정하지 않고 변수를 선언할 수 있습니다.  대신 컴파일러에서는 초기화 식의 형식에서 변수 형식을 유추합니다.  자세한 내용은 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하십시오.  
  
## 값 할당  
 다음 예제에서처럼 대입문을 사용하여 계산을 수행하고 해당 결과를 변수에 할당합니다.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/visualbasic/index_1.vb)]  
  
> [!NOTE]
>  이 예제에 사용된 등호\(`=`\)는 같음 연산자가 아닌 할당 연산자이며  변수 `applesSold`에 값을 할당합니다.  
  
 자세한 내용은 [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)을 참조하십시오.  
  
## 변수 및 속성  
 *속성*은 변수와 마찬가지로 사용자가 액세스할 수 있는 값을 나타내지만  변수보다 훨씬 복잡합니다.  속성은 해당 값을 설정하고 검색하는 방법을 제어하는 코드 블록을 사용합니다.  자세한 내용은 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)을 참조하십시오.  
  
## 참고 항목  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [변수 문제 해결](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)   
 [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)