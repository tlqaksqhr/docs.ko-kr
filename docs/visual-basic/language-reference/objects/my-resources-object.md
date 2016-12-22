---
title: "My.Resources Object | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.Resources"
  - "My.Resources.MyResources.ResourceManager"
  - "My.Resources.MyResources.Culture"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Resources object"
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# My.Resources Object
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

응용 프로그램의 리소스에 액세스하는 속성 및 클래스를 제공합니다.  
  
## 설명  
 `My.Resources` 개체는 응용 프로그램의 리소스에 대한 액세스를 제공하며, 이를 통해 응용 프로그램의 리소스를 동적으로 검색할 수 있습니다.  자세한 내용은 [응용 프로그램 리소스 관리\(.NET\)](/visual-studio/ide/managing-application-resources-dotnet)를 참조하십시오.  
  
 `My.Resources` 개체는 전역 리소스만 노출합니다.  이 개체는 폼과 연관된 리소스 파일에 대한 액세스를 제공하지 않습니다.  폼 리소스에는 폼에서 액세스해야 합니다.  자세한 내용은 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5)를 참조하십시오.  
  
 `My.Resources` 개체에서 응용 프로그램의 문화권별 리소스 파일에 액세스할 수 있습니다.  기본적으로 `My.Resources` 개체는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> 속성에 있는 문화권과 일치하는 리소스 파일에서 리소스를 찾습니다.  그러나 이러한 동작을 무시하고 리소스에 사용할 특정 문화권을 지정할 수 있습니다.  자세한 내용은 [데스크톱 응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하십시오.  
  
## 속성  
 `My.Resources` 개체의 속성은 응용 프로그램의 리소스에 대한 읽기 전용 액세스를 제공합니다.  리소스를 추가하거나 제거하려면 **프로젝트 디자이너**를 사용합니다.  자세한 내용은 [How to: Add or Remove Resources](http://msdn.microsoft.com/ko-kr/7b77bc06-3952-4799-b029-def3f8f7f88d)를 참조하십시오.  `My.Resources.``resourceName`을 사용하여 **프로젝트 디자이너**를 통해 추가된 리소스에 액세스할 수 있습니다.  
  
 또한 **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **새 항목 추가** 또는 **기존 항목 추가**를 클릭하여 리소스 파일을 추가하거나 제거할 수 있습니다.  `My.Resources.``resourceFileName`.`resourceName`을 사용하여 이러한 방법으로 추가된 리소스에 액세스할 수 있습니다.  
  
 각 리소스에는 이름, 범주 및 값이 들어 있으며 이러한 리소스 설정은 속성이 `My.Resources` 개체에 나타나는 리소스에 액세스하는 방법을 결정합니다.  **프로젝트 디자이너**에서 추가된 리소스의 경우에는 다음과 같습니다.  
  
-   이름은 속성의 이름을 결정합니다.  
  
-   리소스 데이터는 속성의 값입니다.  
  
-   범주는 속성의 형식을 결정합니다.  
  
|||  
|-|-|  
|범주|속성 데이터 형식|  
|**문자열**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**이미지**|<xref:System.Drawing.Bitmap>|  
|**아이콘**|<xref:System.Drawing.Icon>|  
|**오디오**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream> 클래스는 <xref:System.IO.Stream> 클래스에서 파생되므로 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> 메서드와 같은 스트림을 가져오는 메서드와 함께 사용할 수 있습니다.|  
|**Files**|-   텍스트 파일용 [문자열](../../../visual-basic/language-reference/data-types/string-data-type.md)<br />-   이미지 파일용 <xref:System.Drawing.Bitmap><br />-   아이콘 파일용 <xref:System.Drawing.Icon><br />-   사운드 파일용 <xref:System.IO.UnmanagedMemoryStream>|  
|**기타**|디자이너의 **형식** 열에 있는 정보에 의해 결정됩니다.|  
  
## 클래스  
 `My.Resources` 개체는 공유 속성을 가진 클래스로 각 리소스 파일을 노출합니다.  클래스 이름은 리소스 파일의 이름과 같습니다.  이전 단원에서 설명한 바와 같이 리소스 파일에 있는 리소스는 클래스에 속성으로 노출됩니다.  
  
## 예제  
 예제 명명 된 문자열 리소스에는 폼의 제목을 `Form1Title` 응용 프로그램 리소스 파일에서입니다.  이때 작업을 응용 프로그램 이라는 문자열이 있어야 합니다 `Form1Title` 리소스 파일에서입니다.  자세한 내용은 [How to: Add or Remove Resources](http://msdn.microsoft.com/ko-kr/7b77bc06-3952-4799-b029-def3f8f7f88d)를 참조하십시오.  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## 예제  
 이 예제에서는 응용 프로그램의 리소스 파일에 저장된 `Form1Icon`이라는 아이콘에 폼의 아이콘을 설정합니다.  이 때, 응용 프로그램 이라는 아이콘이 있어야 `Form1Icon` 리소스 파일에서입니다.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## 예제  
 이 예제에서는 폼의 배경 이미지 라는 이미지 리소스를 설정 하는 `Form1Background`, 응용 프로그램 리소스 파일에 있는.  이 예제에서는 작업을 이라는 이미지 리소스는 응용 프로그램이 있어야 합니다 `Form1Background` 리소스 파일에서입니다.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## 예제  
 라는 이름의 오디오 리소스로 저장 된 소리를 재생 하는이 예제 `Form1Greeting` 응용 프로그램의 리소스 파일.  이때 작업을 응용 프로그램 이라는 오디오 리소스가 있어야 합니다 `Form1Greeting` 리소스 파일에서입니다.  `My.Computer.Audio.Play` 메서드는 Windows Forms 응용 프로그램에만 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## 예제  
 이 예제에서는 응용 프로그램의 문자열 리소스의 프랑스어 culture 버전을 검색합니다.  자원 인 `Message`.  문화권을 변경 하는 `My.Resources` 개체를 사용 하 여,이 예제를 사용 하 여 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 이 예제에서는 작업을 이라는 문자열은 응용 프로그램이 있어야 합니다 `Message` 에서 해당 리소스 파일과 응용 프로그램 Resources.fr FR.resx 리소스 파일의 프랑스어 culture 버전 있어야 합니다.  자세한 내용은 [How to: Add or Remove Resources](http://msdn.microsoft.com/ko-kr/7b77bc06-3952-4799-b029-def3f8f7f88d)를 참조하십시오.  응용 프로그램에 리소스 파일의 프랑스어 culture 버전 없는 경우는 `My.Resource` 개체 기본 culture 리소스 파일에서 리소스를 검색 합니다.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## 참고 항목  
 [How to: Add or Remove Resources](http://msdn.microsoft.com/ko-kr/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [응용 프로그램 리소스 관리\(.NET\)](/visual-studio/ide/managing-application-resources-dotnet)   
 [데스크톱 응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)   
 [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5)