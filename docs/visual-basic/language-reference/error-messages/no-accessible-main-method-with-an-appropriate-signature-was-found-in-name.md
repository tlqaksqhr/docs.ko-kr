---
title: 액세스 가능한 &#39;Main&#39; 에 있는 적절 한 시그니처가 메서드가 &#39; &lt;이름&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6a60e26a2bd0e31c0f92dbbfb2518c75f304d9f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593222"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>액세스 가능한 &#39;Main&#39; 에 있는 적절 한 시그니처가 메서드가 &#39; &lt;이름&gt;&#39;
명령줄 응용 프로그램에 있어야는 `Sub Main` 정의 합니다. `Main` 으로 선언 해야 `Public Shared` 또는 클래스에 정의 되어 있는 경우 `Public` 모듈에서 정의 하는 경우.  
  
 **오류 ID:** BC30737  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   정의 `Public Sub Main` 프로젝트에 대 한 프로시저입니다. 로 선언 `Shared` 클래스 내에서 정의 하는 경우에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 프로그램의 구조](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)
