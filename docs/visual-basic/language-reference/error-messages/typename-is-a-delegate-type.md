---
title: "&quot;&lt;typename&gt;&quot; 대리자 형식입니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3d6cc283f7e9815eb9b723a450731998f14b3424
ms.lasthandoff: 03/13/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>'&lt;typename&gt;' 대리자 형식입니다.
'\<유형 이름 > ' 대리자 형식입니다. 대리자 구문에는 인수 목록으로 단일 AddressOf 식만 허용합니다. 종종 AddressOf 식은 대리자 구문 대신 사용할 수 있습니다.  
  
 A `New` 절 대리자 클래스의 인스턴스를 만들고 대리자 생성자는 잘못 된 인수 목록을 제공 합니다.  
  
 하나만 제공할 수 있습니다 `AddressOf` 새 대리자 인스턴스를 만들 때 식입니다.  
  
 전달 하지 않으면 모든 인수는 대리자 생성자에 둘 이상의 인수를 전달 하거나 단일 인수를 전달 하는 경우는 유효 하지 않은 경우이 오류가 발생할 수 있습니다 `AddressOf` 식입니다.  
  
 **오류 ID:** BC32008  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   단일을 사용 하 여 `AddressOf` 대리자 클래스에 대 한 인수 목록에서 식의 `New` 절.  
  
## <a name="see-also"></a>참고 항목  
 [New 연산자](../../../visual-basic/language-reference/operators/new-operator.md)   
 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [방법: 대리자 메서드 호출](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
