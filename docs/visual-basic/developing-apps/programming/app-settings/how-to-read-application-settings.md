---
title: "방법: Visual Basic에서 응용 프로그램 설정 읽기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reading application settings
- My.Settings object, reading application settings
- application settings, reading
ms.assetid: eb3428ef-115e-49a8-a878-e0613183fee0
caps.latest.revision: 12
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e5ad120e52896476447d892438ed9a5d2979da8c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-application-settings-in-visual-basic"></a>방법: Visual Basic에서 응용 프로그램 설정 읽기
`My.Settings` 개체에서 설정의 속성에 액세스하여 사용자 설정을 읽을 수 있습니다.  
  
 `My.Settings` 개체는 각 설정을 속성으로 표시합니다. 속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다. 설정의 **범위**는 속성이 읽기 전용인지 여부를 나타냅니다. **응용 프로그램** 범위 설정의 속성은 읽기 전용이지만 **사용자** 범위 설정의 속성은 읽기-쓰기입니다. 자세한 내용은 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 `Nickname` 설정의 값을 표시합니다.  
  
 [!code-vb[VbVbalrMyResources#14](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-read-application-settings_1.vb)]  
  
 이 예제가 작동하려면 응용 프로그램에 `String` 형식의 `Nickname` 설정이 있어야 합니다. 자세한 내용은 [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [My.Settings 개체](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [방법: Visual Basic에서 사용자 설정 변경](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [방법: Visual Basic에서 사용자 설정 유지](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
