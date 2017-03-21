---
title: "My.Resources 개체 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
dev_langs:
- VB
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
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
ms.openlocfilehash: 6ad5bd4e33438256719b59cb0936cf6bc8525ab1
ms.lasthandoff: 03/13/2017

---
# <a name="myresources-object"></a>My.Resources 개체
응용 프로그램의 리소스에 액세스 하기 위한 속성 및 클래스를 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 사용 하면 동적으로 응용 프로그램에 대 한 리소스를 검색 합니다. 자세한 내용은 참조 [응용 프로그램 리소스 관리 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)합니다.  
  
 `My.Resources` 개체는 전역 리소스에만 표시 합니다. 폼과 관련 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다. 폼에서 폼 리소스에 액세스 해야 합니다. 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)를 참조하세요.  
  
 응용 프로그램의 문화권 관련 리소스 파일에서 액세스할 수는 `My.Resources` 개체입니다. 기본적으로는 `My.Resources` 개체 culture에 일치 하는 리소스 파일에서 리소스를 찾는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>속성.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> 그러나이 동작을 재정의할 수 있으며 리소스에 대해 사용 하 여 특정 문화권을 지정할 수 있습니다. 자세한 내용은 참조 [데스크톱 응용 프로그램의 리소스](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)합니다.  
  
## <a name="properties"></a>속성  
 속성은 `My.Resources` 개체는 응용 프로그램의 리소스에 대 한 읽기 전용 액세스를 제공 합니다. 를 추가 하거나 리소스를 제거 하는 **프로젝트 디자이너**합니다. 자세한 내용은 참조 [하는 방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)합니다. 통해 추가 리소스에 액세스할 수는 **프로젝트 디자이너** 를 사용 하 여 `My.Resources.``resourceName`합니다.  
  
 추가 하거나에서 프로젝트를 선택 하 여 리소스 파일을 제거할 수도 있습니다 **솔루션 탐색기** 클릭 하 고 **새 항목 추가** 또는 **기존 항목 추가** 에서 **프로젝트** 메뉴. 이 방식으로 사용 하 여 추가 리소스에 액세스할 수 `My.Resources.``resourceFileName`.`resourceName`합니다.  
  
 각 리소스는 이름, 범주 및 값을 포함 하며 이러한 리소스 설정에 따라 리소스를 액세스 하는 속성에 표시 되는 방식을 결정은 `My.Resources` 개체입니다. 추가 된 리소스에 대 한는 **프로젝트 디자이너**:  
  
-   이름, 속성의 이름이 결정  
  
-   리소스 데이터는 속성의 값  
  
-   범주는 속성의 유형을 결정합니다.  
  
|범주|속성 데이터 형식|  
|---|---|  
|**문자열**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**이미지**|<xref:System.Drawing.Bitmap></xref:System.Drawing.Bitmap>|  
|**아이콘**|<xref:System.Drawing.Icon></xref:System.Drawing.Icon>|  
|**오디오**|<xref:System.IO.UnmanagedMemoryStream></xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream>클래스에서 파생 되는 <xref:System.IO.Stream>와 같은 스트림를 사용 하는 메서드와 함께 사용할 수 있도록 클래스는 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>메서드.</xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> </xref:System.IO.Stream> </xref:System.IO.UnmanagedMemoryStream>|  
|**파일**|-   [문자열](../../../visual-basic/language-reference/data-types/string-data-type.md) 텍스트 파일입니다.<br />- <xref:System.Drawing.Bitmap>이미지 파일에 대 한.</xref:System.Drawing.Bitmap><br />- <xref:System.Drawing.Icon>아이콘 파일에 대 한.</xref:System.Drawing.Icon><br />- <xref:System.IO.UnmanagedMemoryStream>사운드 파일에 대 한.</xref:System.IO.UnmanagedMemoryStream>|  
|**기타**|디자이너의 정보에 의해 결정 **형식** 열입니다.|  
  
## <a name="classes"></a>클래스  
 `My.Resources` 공유 속성을 사용 하 여 클래스와 각 리소스 파일을 노출 하는 개체입니다. 클래스 이름을 리소스 파일의 이름과 같습니다. 이전 섹션에서 설명한 대로, 리소스 파일의 리소스 클래스에 속성으로 노출 됩니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 폼의 제목 이라는 문자열 리소스가 설정 `Form1Title` 응용 프로그램 리소스 파일에 있습니다. 이 예제에서 응용 프로그램 이라는 문자열 있어야 `Form1Title` 의 리소스 파일에 있습니다. 자세한 내용은 참조 [하는 방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)합니다.  
  
 [!code-vb[VbVbalrMyResources #&1;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>예제  
 이 예제에서는 명명 된 아이콘을 폼의 아이콘 설정 `Form1Icon` 하는 응용 프로그램의 리소스 파일에 저장 됩니다. 이 예제에서에 대 한 응용 프로그램에 있어야 라는 아이콘 `Form1Icon` 의 리소스 파일에 있습니다.  
  
 [!code-vb[VbVbalrMyResources #&2;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>예제  
 명명 된 이미지 리소스를 폼의 배경 이미지를 설정 하는이 예제 `Form1Background`, 응용 프로그램 리소스 파일에 있습니다. 이 예제가 작동 하려면 응용 프로그램에 있어야 라는 이미지 리소스 `Form1Background` 의 리소스 파일에 있습니다.  
  
 [!code-vb[VbVbalrMyResources #&3;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>예제  
 이 예제에서는 명명 된 오디오 리소스로 저장 된 소리를 재생 `Form1Greeting` 응용 프로그램의 리소스 파일에 있습니다. 이 예제에서 응용 프로그램 이라는 오디오 리소스가 있어야 `Form1Greeting` 의 리소스 파일에 있습니다. `My.Computer.Audio.Play` 메서드는 Windows Forms 응용 프로그램에만 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrMyResources #&4;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>예제  
 이 예에서는 프랑스어 문화권 버전의 응용 프로그램의 문자열 리소스를 검색합니다. 리소스 이름은 `Message`합니다. Culture를 변경 하는 `My.Resources` 개체를 사용 하 여,이 예제에서는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> 사용  
  
 이 예제가 작동 하려면 응용 프로그램에 있어야 라는 문자열 `Message` 리소스 파일과 응용 프로그램 없어야 Resources.fr-FR.resx 해당 리소스 파일의 프랑스어 문화권 버전입니다. 자세한 내용은 참조 [하는 방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)합니다. 응용 프로그램 리소스 파일의 프랑스어 문화권 버전이 없는 경우는 `My.Resource` 개체는 기본 문화권 리소스 파일에서 리소스를 검색 합니다.  
  
 [!code-vb[VbVbalrMyResources #&10;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [응용 프로그램 리소스 (.NET) 관리](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)   
 [데스크톱 앱의 리소스](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)   
 [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)
