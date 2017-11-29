---
title: "&#39; &lt;typename&gt;&#39; 대리자 형식이"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords: BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39; &lt;typename&gt;&#39; 대리자 형식이
'\<형식 이름 >' 대리자 형식이 있습니다. 대리자 구문에는 인수 목록으로 단일 AddressOf 식만 허용합니다. 종종 AddressOf 식은 대리자 구문 대신 사용할 수 있습니다.  
  
 A `New` 대리자 클래스의 인스턴스를 만드는 절 대리 생성자에는 잘못 된 인수 목록을 제공 합니다.  
  
 한 번만 제공할 수 있습니다 `AddressOf` 새 대리자 인스턴스를 만들 때 식입니다.  
  
 전달 하지 않으면 모든 인수는 대리 생성자에 단일 인수를 전달 하는 경우 올바르지 않은 한 또는 둘 이상의 인수를 전달 하는 경우이 오류가 발생할 수 있습니다 `AddressOf` 식입니다.  
  
 **오류 ID:** BC32008  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   단일을 사용 하 여 `AddressOf` 대리자 클래스에 대 한 인수 목록에서 식의 `New` 절.  
  
## <a name="see-also"></a>참고 항목  
 [New 연산자](../../../visual-basic/language-reference/operators/new-operator.md)  
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [방법: 대리자 메서드 호출](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
