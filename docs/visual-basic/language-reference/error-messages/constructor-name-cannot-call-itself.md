---
title: "생성자 &#39; &lt;이름&gt;&#39; 자신을 호출할 수 없습니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords: BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>생성자 &#39; &lt;이름&gt;&#39; 자신을 호출할 수 없습니다
A `Sub New` 클래스 또는 구조체에는 프로시저가 자신을 호출 합니다.  
  
 클래스의 인스턴스를 초기화 하는 생성자의 목적은 또는 구조가 처음 생성 합니다. 클래스 또는 구조체는 다른 매개 변수 목록을 모두 있는 여러 생성자에 있을 수 있습니다. 생성자 자체 외에도 해당 기능을 수행 하려면 다른 생성자를 호출할 수 있습니다. 자신을 호출 하는 생성자에 대 한 의미가 없습니다 있고 실제로 초래 무한 재귀가 허용 합니다.  
  
 **오류 ID:** BC30298  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  호출 중인 생성자의 매개 변수 목록을 확인 합니다. 전화 통화를 걸기 생성자의 달라 야 합니다.  
  
2.  다른 생성자를 호출 하지 않을 경우 제거 된 `Sub New` 전적으로 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 수명: 개체가 만들어지고 제거되는 방법](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
