---
title: 프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07233ed1c68f85878ffdd7131f64e30e158dc350
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생했습니다.
프로젝트에서 XML 스키마를 컴파일하는 동안 오류가 발생 했습니다. 이 인해 XML IntelliSense를 사용할 수 없습니다.  
  
 프로젝트에 포함 하는 XML XSD (스키마 정의) 스키마에 오류가 있습니다. 이 오류는 프로젝트에 대해 설정 된 기존 XSD 스키마와 충돌 하는 XSD 스키마 (.xsd) 파일을 추가할 때 발생 합니다.  
  
 **오류 ID:** BC36810  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   경고를 두 번 클릭은 **오류 목록** 창. Visual Basic 경고의 원인이 되는 XSD 파일의 위치로 이동 합니다. XSD 스키마에서 오류를 수정 합니다.  
  
-   필요한 모든 프로젝트에 포함 된 XSD 스키마 (.xsd) 파일을 확인 합니다. 클릭 해야 **모든 파일 표시** 에 **프로젝트** 메뉴를 보려면.xsd 파일 **솔루션 탐색기**합니다. .Xsd 파일을 마우스 오른쪽 단추로 누른 **프로젝트에 포함** 프로젝트에서 파일을 포함 하도록 합니다.  
  
-   XML to Schema 마법사를 사용 하는 경우 동일한 원본에서 스키마를 한 번 이상 유추한 경우이 오류가 발생할 수 있습니다. 이 경우 스키마 항목 템플릿을에 새 XML를 추가 하면 프로젝트에서 기존 XSD 스키마 파일을 제거할 수 있습니다 한 다음 XML to Schema 마법사를 제공할 적용 가능한 모든 XML 소스 프로젝트에 대 한 합니다.  
  
-   오류가 발생 하지는 XSD 스키마에 식별 되 면 XML 컴파일러는 자세한 오류 메시지를 제공할 수 있는 충분 한 정보가 없을 수 있습니다. .Xsd 파일에 대 한 XML 네임 스페이스에에서 포함 되어 있는지 프로젝트 일치 Visual Studio에서 설정 된 XML 스키마에 대 한 식별 된 XML 네임 스페이스를 확인 하는 경우 자세한 오류 정보를 얻을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 목록 창](/visualstudio/ide/reference/error-list-window)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
