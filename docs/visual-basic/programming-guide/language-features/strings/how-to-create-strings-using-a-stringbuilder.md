---
title: "방법: Visual Basic에서 StringBuilder를 사용하여 문자열 만들기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c799794b319843b0239ce9589e0c556c603c8617
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>방법: Visual Basic에서 StringBuilder를 사용하여 문자열 만들기
사용 하 여 여러 개의 짧은 문자열에서 긴 문자열을 구성 하는이 예제는 <xref:System.Text.StringBuilder> 클래스입니다. <xref:System.Text.StringBuilder> 클래스 보다 더 효율적입니다.는 `&=` 많은 문자열을 연결 하기 위한 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 인스턴스는 <xref:System.Text.StringBuilder> 클래스, 1, 000 문자열 해당 인스턴스에 추가 하 고 다음 문자열 표현을 반환 합니다.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [StringBuilder 클래스 사용](../../../../standard/base-types/stringbuilder.md)  
 [&= 연산자](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [문자열](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [새 문자열 만들기](../../../../standard/base-types/creating-new.md)  
 [문자열 조작](../../../../standard/base-types/manipulating-strings.md)  
 [문자열 샘플](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)
