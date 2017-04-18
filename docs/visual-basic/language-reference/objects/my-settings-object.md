---
title: "My.Settings 개체 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
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
ms.openlocfilehash: d48d3556f55ef286e2f501e2df5bf5035d3aff90
ms.lasthandoff: 03/13/2017

---
# <a name="mysettings-object"></a>My.Settings 개체
응용 프로그램의 설정에 액세스 하기 위한 메서드와 속성을 제공 합니다.  
  
## <a name="remarks"></a>주의  
 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 하 고 동적으로 저장 하 고 속성 설정 및 응용 프로그램에 대 한 기타 정보를 검색할 수 있습니다. 자세한 내용은 참조 [응용 프로그램 설정 관리 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)합니다.  
  
## <a name="properties"></a>속성  
 속성은 `My.Settings` 개체 응용 프로그램의 설정에 대 한 액세스를 제공 합니다. 를 추가 하거나 설정을 제거는 **설정 디자이너**합니다.  
  
 각 설정에는 **이름**, **형식**, **범위**, 및 **값**, 이러한 설정은 각 설정에 액세스 하는 속성에 표시 되는 방식을 결정 하 고는 `My.Settings` 개체:  
  
-   **이름** 속성의 이름을 결정 합니다.  
  
-   **형식** 속성의 유형을 결정 합니다.  
  
-   **범위** 읽기 전용 속성 인지 여부를 나타냅니다. 값이 **응용 프로그램**, 속성은 읽기 전용 이면 값이 **사용자**, 속성은 읽기 / 쓰기입니다.  
  
-   **값** 속성의 기본값입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|---|---|  
|`Reload`|마지막으로 저장 된 값에서 사용자 설정을 다시 로드합니다.|  
|`Save`|현재 사용자 설정을 저장합니다.|  
  
 `My.Settings` 고급 속성 및 메서드를 <xref:System.Configuration.ApplicationSettingsBase>클래스</xref:System.Configuration.ApplicationSettingsBase> 에서 상속 된 개체 제공  
  
## <a name="tasks"></a>작업  
 다음 표에서 관련 된 작업의 예제는 `My.Settings` 개체입니다.  
  
|후|참조|  
|---|---|  
|응용 프로그램 설정 읽기|[방법: Visual Basic의 응용 프로그램 설정 읽기](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|사용자 설정 변경|[방법: Visual Basic에서 사용자 설정 변경](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|사용자 설정 유지|[방법: Visual Basic에서 사용자 설정 유지](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|사용자 설정에 대 한 속성 표 만들기|[방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>예제  
 값을 표시 하는이 예제는 `Nickname` 설정 합니다.  
  
 [!code-vb[VbVbalrMyResources #&14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 이 예제가 작동 하려면 응용 프로그램 있어야는 `Nickname` 유형의 설정 `String`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase>   
 [방법: Visual Basic의 응용 프로그램 설정 읽기](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [방법: Visual Basic에서 사용자 설정 변경](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [방법: Visual Basic에서 사용자 설정 유지](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [방법: Visual Basic에서 사용자 설정의 속성 표 만들기](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)   
 [응용 프로그램 설정 관리(.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)
