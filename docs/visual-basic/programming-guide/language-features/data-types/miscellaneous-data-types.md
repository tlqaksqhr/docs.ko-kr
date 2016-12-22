---
title: "Miscellaneous Data Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "Object data type, data types"
  - "data types [Visual Basic], choosing"
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Miscellaneous Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 숫자나 문자로 분류되지 않는 여러 데이터 형식을 제공합니다.  이러한 데이터 형식은 yes\/no 값, 날짜\/시간 값 및 개체 주소와 같은 특수 데이터를 처리합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 데이터 형식을 비교한 표를 보려면 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)을 참조하십시오.  
  
## Boolean 형식  
 [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)은 `True`나 `False`로 해석되는 부호 없는 값입니다.  데이터 너비는 구현하는 플랫폼에 따라 다릅니다.  변수가 true\/false, yes\/no 또는 on\/off 등의 두 상태로 된 값만 가질 수 있는 경우에는 변수를 `Boolean`으로 선언합니다.  
  
## Date 형식  
 [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md)은 날짜와 시간 정보가 모두 있는 64비트 값입니다.  각 증분은 그레고리오력으로 1년 1월 1일 시작\(12:00 AM\)부터 경과한 시간의 100 나노초 단위를 나타냅니다.  변수가 날짜 값, 시간 값 또는 둘 다를 가질 수 있는 경우에는 변수를 `Date`로 선언합니다.  
  
## Object 형식  
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)은 응용 프로그램이나 일부 다른 응용 프로그램에 있는 개체 인스턴스를 가리키는 32비트 주소입니다.  `Object` 변수는 응용 프로그램에서 인식할 수 있는 개체나 모든 데이터 형식의 데이터를 참조할 수 있습니다.  여기에 둘 다  *값 형식*, 같은 `Integer`, `Boolean`, 및 구조체 인스턴스를 및  *참조 형식*, 어떤 같은 클래스에서 생성 된 개체의 인스턴스는 `String` 및 <xref:System.Windows.Forms.Form>, 및 인스턴스는 배열.  
  
 변수가 컴파일 타임에는 알 수 없는 클래스 인스턴스에 대한 포인터를 저장하거나 다양한 데이터 형식의 데이터를 가리킬 수 있는 경우에는 변수를 `Object`로 선언합니다.  
  
 장점이 있는 `Object` 입니다 하면이 모든 데이터 형식의 데이터를 저장할 수 있는 데이터입니다.  그러나 추가 연산이 수행되므로 실행 시간이 오래 걸리고 응용 프로그램의 성능이 느려진다는 단점도 있습니다.  `Object` 변수를 값 형식에 사용하면 *boxing* 및 *unboxing*이 수행되고,  참조 형식에 사용하면 *런타임에 바인딩*이 수행됩니다.  
  
## 참고 항목  
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Character Data Types](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)