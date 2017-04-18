---
title: "너무 많은 클라이언트에서 DLL 응용 프로그램 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1abc9ce574de00db42a33cde478ca80be74e61ff
ms.lasthandoff: 03/13/2017

---
# <a name="too-many-dll-application-clients"></a>DLL 응용 프로그램 클라이언트가 너무 많습니다.
동적 연결 라이브러리 (DLL)에 대 한 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 제한 된 수의 응용 프로그램을 호스트 하 여만 액세스를 허용 합니다. 응용 프로그램 및 다른 응용 프로그램을 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 호스트 (의 일부는 액세스할 수 있는 응용 프로그램)에 액세스 하는 모든는 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 동시에 DLL입니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   열려 있는 응용 프로그램에 액세스할 수를 줄일 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 형식](../../visual-basic/programming-guide/language-features/error-types.md)
