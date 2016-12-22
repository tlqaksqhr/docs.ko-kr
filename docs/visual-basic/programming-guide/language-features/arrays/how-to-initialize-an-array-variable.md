---
title: "How to: Initialize an Array Variable in Visual Basic | Microsoft Docs"
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
  - "variables [Visual Basic], initializing"
  - "arrays [Visual Basic], variables"
  - "arrays [Visual Basic], initializing"
  - "arrays [Visual Basic], declaring"
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: 42
caps.handback.revision: 42
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Initialize an Array Variable in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`New` 절에 배열 리터럴 포함하고 배열의 초기 값을 지정하여 배열 변수를 초기화합니다.  형식을 지정하거나 배열 리터럴의 값에서 유추하도록 할 수 있습니다.  형식 유추 방법에 대한 자세한 내용은 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)에서 "배열에 초기 값 채우기"를 참조하십시오.  
  
### 배열 리터럴을 사용하여 배열 변수를 초기화하려면  
  
-   `New` 절에서 또는 배열 값을 할당할 때 중괄호\(`{}`\) 안에 요소 값을 제공합니다.  다음 예제에서는 `Char` 형식의 요소가 있는 배열을 포함하는 변수를 선언하고, 만들고, 초기화하는 여러 가지 방법을 보여 줍니다.  
  
     [!CODE [VbVbalrArrays#16](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#16)]  
  
     각 문을 실행한 후 만들어지는 배열의 길이는 3이고, 인덱스 0부터 인덱스 2까지의 요소에 초기 값이 포함됩니다.  상한과 해당 값을 모두 지정할 경우에는 인덱스 0부터 상한까지의 모든 요소에 대한 값을 포함해야 합니다.  
  
     배열 리터럴에 요소 값을 제공한 경우에는 인덱스 상한을 지정할 필요가 없습니다.  상한을 지정하지 않으면 배열 리터럴의 값 개수를 기반으로 배열의 크기가 유추됩니다.  
  
### 배열 리터럴을 사용하여 다차원 배열 변수를 초기화하려면  
  
-   중괄호\(`{}`\) 내의 중괄호 안에 값을 중첩합니다.  중첩된 배열 리터럴은 모두 동일한 형식과 길이의 배열로 유추됩니다.  다음 코드 예제에서는 다차원 배열을 초기화하는 몇 가지 예를 보여 줍니다.  
  
     [!CODE [VbVbalrArrays#17](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#17)]  
  
-   명시적으로 배열 범위를 지정하거나, 그대로 두고 컴파일러에서 배열 리터럴의 값을 기반으로 배열 범위를 유추하게 할 수 있습니다.  상한과 해당 값을 모두 지정할 경우에는 모든 차원의 인덱스 0부터 상한까지의 모든 요소에 대한 값을 포함해야 합니다.  다음 예제에서는 `Short` 형식의 요소가 있는 2차원 배열을 포함하는 변수를 선언하고, 만들고, 초기화하는 여러 가지 방법을 보여 줍니다.  
  
     [!CODE [VbVbalrArrays#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#18)]  
  
     각 문을 실행한 후 만들어지는 배열에는 인덱스가 각각 `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)` 및 `(1,2)`인 6개의 초기화된 요소가 포함됩니다.  각 배열 위치에는 값 `10`이 포함됩니다.  
  
-   다음 예제는 다차원 배열을 반복합니다.  Visual Basic으로 작성된 Windows 콘솔 응용 프로그램에서 코드를 `Sub Main()` 메서드 내에 붙여 넣습니다.  마지막 주석은 출력을 나타냅니다.  
  
     [!CODE [VbVbalrArrays#31](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#31)]  
  
### 배열 리터럴을 사용하여 가변 배열 변수를 초기화하려면  
  
-   중괄호\(`{}`\) 안에 개체 값을 중첩합니다.  길이가 다른 배열을 지정하는 배열 리터럴을 중첩할 수도 있지만, 가변 배열의 경우 중첩된 배열 리터럴을 괄호\(`()`\)로 묶어야 합니다.  괄호를 사용하면 중첩된 배열 리터럴이 강제로 계산되고, 결과 배열이 가변 배열의 초기 값으로 사용됩니다.  다음 코드 예제에서는 가변 배열을 초기화하는 두 가지 예를 보여 줍니다.  
  
     [!CODE [VbVbalrArrays#19](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#19)]  
  
-   다음 예제는 가변 배열을 합니다.  Visual Basic으로 작성된 Windows 콘솔 응용 프로그램에서 코드를 `Sub Main()` 메서드 내에 붙여 넣습니다.  코드의 마지막 주석은 출력을 나타냅니다.  
  
     [!CODE [VbVbalrArrays#32](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrArrays#32)]  
  
## 참고 항목  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)