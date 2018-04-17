---
title: '방법: Visual Basic에서 StringBuilder를 사용하여 문자열 만들기'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0e15c7df07822ee104a88525c209768c05470e3
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
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
 [문자열 샘플](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))
