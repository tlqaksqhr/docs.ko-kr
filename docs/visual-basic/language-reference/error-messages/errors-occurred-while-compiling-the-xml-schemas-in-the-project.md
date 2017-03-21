---
title: "프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다. | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: cf04e85da98db53d1c78269169571936f708cd21
ms.lasthandoff: 03/13/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.
프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다. 이 때문에 XML IntelliSense를 사용할 수 없습니다.  
  
 프로젝트에 포함 하는 XML XSD (스키마 정의) 스키마에 오류가 있습니다. 이 오류는 프로젝트에 대해 설정 된 기존 XSD 스키마를 사용 하 여 충돌 하는 XSD 스키마 (.xsd) 파일을 추가할 때 발생 합니다.  
  
 **오류 ID:** BC36810  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   경고를 두 번 클릭은 **오류 목록** 창입니다. Visual Basic 경고의 원인이 되는 XSD 파일의 위치로 이동 합니다. XSD 스키마에서 오류를 수정 합니다.  
  
-   필요한 모든 XSD 스키마 (.xsd) 파일은 프로젝트에 포함 했는지 확인 합니다. 클릭 해야 할 수도 **모든 파일 표시** 에 **프로젝트** .xsd를 메뉴에 파일 **솔루션 탐색기**합니다. .Xsd 파일을 마우스 오른쪽 단추로 누른 **프로젝트에 포함** 를 프로젝트에 파일을 포함 합니다.  
  
-   XML to Schema 마법사를 사용 하는 동일한 소스에서 스키마를 한 번 이상 유추한 하는 경우이 오류가 발생할 수 있습니다. 이 경우 프로젝트에서 기존 XSD 스키마 파일을 제거할 수 있습니다 스키마 항목 템플릿에 새 XML 추가 하 고 XML을 입력 스키마 마법사, 적용 가능한 모든 XML 소스와 프로젝트에 대 한 키를 누릅니다.  
  
-   오류가 발생 하지는 XSD 스키마에서 식별 되 면 XML 컴파일러는 자세한 오류 메시지를 제공할 수 있는 충분 한 정보가 없을 수 있습니다. .Xsd 파일에 대 한 XML 네임 스페이스에에서 포함 되도록 프로젝트 일치를 사용 하 여 Visual Studio에서 설정 된 XML 스키마에 대해 식별 된 XML 네임 스페이스를 확인 하는 경우 자세한 오류 정보를 얻을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 목록 창](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window)   
 [Visual Basic의 XML IntelliSense](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
