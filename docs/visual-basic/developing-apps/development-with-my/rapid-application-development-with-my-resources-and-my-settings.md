---
title: My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 808e02510d4f0a237ad4354b2edac8fa024b5f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발(Visual Basic)
`My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 응용 프로그램에 대 한 리소스를 동적으로 검색할 수 있습니다.  
  
## <a name="retrieving-resources"></a>리소스 검색  
 다양 한 리소스 오디오 파일, 아이콘, 이미지, 문자열 등을 통해 검색할 수 있습니다는 `My.Resources` 개체입니다. 예를 들어 응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다. 다음 예제에서는 명명 된 아이콘을 폼의 아이콘 설정 `Form1Icon` 응용 프로그램의 리소스 파일에 저장 합니다.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources` 만 전역 리소스를 노출 하는 개체입니다. 폼과 연관 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다. 폼에서 폼 리소스에 액세스 해야 합니다.  
  
 마찬가지로,는 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 기타 정보를 검색할 수 있습니다. 자세한 내용은 참조 [My.Resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md) 및 [My.Settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [My.Resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [My.Settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [응용 프로그램 설정 액세스](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
