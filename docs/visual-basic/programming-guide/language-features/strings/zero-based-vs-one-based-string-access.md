---
title: "Zero-based vs. One-based String Access in Visual Basic | Microsoft Docs"
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
  - "strings [Visual Basic], indexing"
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Zero-based vs. One-based String Access in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]을 사용하여 문자열의 문자에 액세스하는 방법과 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]를 사용하여 문자열의 문자에 액세스하는 방법을 비교합니다.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]에서는 항상 0부터 시작하여 문자열의 문자에 액세스하지만, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 함수에 따라 0부터 시작하여 액세스하거나 1부터 시작하여 액세스합니다.  
  
## 1부터 시작  
 1부터 시작하는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 함수의 예로는 `Mid` 함수가 있습니다.  이 함수는 부분 문자열이 시작하는 문자 위치를 나타내는 인수를 사용합니다. 이 문자 위치는 1부터 시작됩니다.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=fullName> 메서드는 문자열에서 부분 문자열의 첫 번째 문자의 인덱스를 사용합니다. 이 인덱스는 0부터 시작됩니다.  따라서 문자열 "ABCDE"를 `Mid` 함수에서 사용할 경우 개별 문자의 번호는 1,2,3,4,5로 지정되지만 <xref:System.String.Substring%2A?displayProperty=fullName> 메서드에서 사용할 경우에는 번호가 0,1,2,3,4로 지정됩니다.  
  
## 0부터 시작  
 0부터 시작하는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 함수의 예로는 `Split` 함수가 있습니다.  이 함수는 문자열을 분할하고 부분 문자열이 포함된 배열을 반환합니다.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=fullName> 메서드도 문자열을 분할하고 부분 문자열이 포함된 배열을 반환합니다.  `Split` 함수와 <xref:System.String.Split%2A> 메서드는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 배열을 반환하기 때문에 0부터 시작해야 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A>   
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)