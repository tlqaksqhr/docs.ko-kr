---
title: "How to: Create Property Grids for User Settings in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings object, creating property grids for user settings"
  - "user settings, creating property grids"
  - "property grids, creating for user settings"
  - "property grids"
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Create Property Grids for User Settings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Windows.Forms.PropertyGrid> 컨트롤을 `My.Settings` 개체의 사용자 설정 속성으로 채워서 사용자 설정의 속성 표를 만들 수 있습니다.  
  
> [!NOTE]
>  이 예제가 작동하려면 응용 프로그램의 사용자 설정이 구성되어 있어야 합니다.  자세한 내용은 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)을 참조하십시오.  
  
 `My.Settings` 개체는 각 설정을 속성으로 노출합니다.  속성 이름은 설정 이름과 같고 속성 형식은 설정 형식과 같습니다.  설정의 **범위**에 따라 속성이 읽기 전용인지 결정됩니다. **응응 프로그램** 범위 설정의 속성은 읽기 전용인 반면 **사용자** 범위 설정의 속성은 읽기\/쓰기입니다.  자세한 내용은 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)을 참조하십시오.  
  
> [!NOTE]
>  응용 프로그램 범위 설정의 값은 런타임에 변경하거나 저장할 수 없습니다.  응용 프로그램 범위 설정은 **프로젝트 디자이너**를 통해 응용 프로그램을 만들 때 또는 응용 프로그램의 구성 파일을 편집하는 방식으로만 변경할 수 있습니다.  자세한 내용은 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)을 참조하십시오.  
  
 이 예제에서는 <xref:System.Windows.Forms.PropertyGrid> 컨트롤을 사용하여 `My.Settings` 개체의 사용자 설정 속성에 액세스합니다.  기본적으로 <xref:System.Windows.Forms.PropertyGrid>는 `My.Settings` 개체의 모든 속성을 표시합니다.  하지만 사용자 설정 속성에는 <xref:System.Configuration.UserScopedSettingAttribute> 특성이 있습니다.  이 예제에서는 <xref:System.Windows.Forms.PropertyGrid>의 <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> 속성을 <xref:System.Configuration.UserScopedSettingAttribute>로 설정하여 사용자 설정 속성만 표시합니다.  
  
### 사용자 설정 속성 표를 추가하려면  
  
1.  **도구 상자**의 **PropertyGrid** 컨트롤을 응용 프로그램의 디자인 화면에 추가합니다. 여기서는  `Form1`에 추가하는 것으로 가정합니다.  
  
     속성 표 컨트롤의 기본 이름은 `PropertyGrid1`입니다.  
  
2.  `Form1`의 디자인 화면을 두 번 클릭하여 폼 로드 이벤트 처리기에 대한 코드를 엽니다.  
  
3.  `My.Settings` 개체를 속성 표에 대해 선택된 개체로 설정합니다.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  사용자 설정만 표시되도록 속성 표를 구성합니다.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  응용 프로그램 범위 설정만 표시 하려면 사용 하는 <xref:System.Configuration.ApplicationScopedSettingAttribute> 특성 대신 <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## 강력한 프로그래밍  
 응용 프로그램은 응용 프로그램이 종료될 때 사용자 설정을 저장합니다.  설정을 즉시 저장하려면 `My.Settings.Save` 메서드를 호출합니다.  자세한 내용은 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)을 참조하십시오.  
  
## 참고 항목  
 [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [How to: Read Application Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [How to: Change User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [응용 프로그램 설정 관리\(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)