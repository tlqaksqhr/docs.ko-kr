---
title: My.Resources 개체
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 9fd23cb119ff9148a45d32ec70ccc4dad08ab876
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="myresources-object"></a>My.Resources 개체
응용 프로그램의 리소스에 액세스 하기 위한 속성 및 클래스를 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 사용 하면 동적으로 응용 프로그램에 대 한 리소스를 검색 합니다. 자세한 내용은 참조 [응용 프로그램 리소스 관리 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)합니다.  
  
 `My.Resources` 만 전역 리소스를 노출 하는 개체입니다. 폼과 연관 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다. 폼에서 폼 리소스에 액세스 해야 합니다.  
  
 응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다는 `My.Resources` 개체입니다. 기본적으로는 `My.Resources` culture에 일치 하는 리소스 파일에서 리소스를 조회 하는 개체는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> 속성입니다. 그러나이 동작을 재정의할 수 있으며 특정 리소스에 사용할 culture를 지정할 수 있습니다. 자세한 내용은 [데스크톱 앱의 리소스](../../../framework/resources/index.md)를 참조하세요.  
  
## <a name="properties"></a>속성  
 속성은 `My.Resources` 개체 응용 프로그램의 리소스에 대 한 읽기 전용 액세스를 제공 합니다. 를 추가 하거나 리소스를 제거 하려면 사용 하 여는 **프로젝트 디자이너**합니다. 통해 추가 된 리소스에 액세스할 수 있습니다는 **프로젝트 디자이너** 를 사용 하 여 `My.Resources.``resourceName`합니다.  
  
 추가 하거나에서 프로젝트를 선택 하 여 리소스 파일을 제거할 수도 **솔루션 탐색기** 클릭 하 고 **새 항목 추가** 또는 **기존 항목 추가** 에서  **프로젝트** 메뉴. 이런이 방식으로 사용 하 여 추가 리소스에 액세스할 수 있습니다 `My.Resources.``resourceFileName`.`resourceName`합니다.  
  
 이러한 리소스 설정에 따라 리소스를 액세스 하는 속성에 표시 되는 방식을 결정 하 고 이름, 범주 및 값을 각 리소스에는 `My.Resources` 개체입니다. 추가 된 리소스에 대 한는 **프로젝트 디자이너**:  
  
-   이름에는 속성의 이름이 결정  
  
-   리소스 데이터는 속성의 값  
  
-   범주에는 속성의 유형을 결정합니다.  
  
|범주|속성 데이터 형식|  
|---|---|  
|**문자열**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**이미지**|<xref:System.Drawing.Bitmap>|  
|**아이콘**|<xref:System.Drawing.Icon>|  
|**오디오**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream> 클래스에서 파생 되는 <xref:System.IO.Stream> 클래스와 같은 스트림를 사용 하는 메서드와 함께 사용할 수 있도록는 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> 메서드.|  
|**파일**|-   [문자열](../../../visual-basic/language-reference/data-types/string-data-type.md) 텍스트 파일에 대 한 합니다.<br />-   <xref:System.Drawing.Bitmap> 이미지 파일입니다.<br />-   <xref:System.Drawing.Icon> 아이콘 파일입니다.<br />-   <xref:System.IO.UnmanagedMemoryStream> 사운드 파일입니다.|  
|**기타**|디자이너에 있는 정보에 의해 결정 **형식** 열입니다.|  
  
## <a name="classes"></a>클래스  
 `My.Resources` 개체 공유 속성을 사용 하 여 클래스와 각 리소스 파일을 노출 합니다. 클래스 이름은 리소스 파일의 이름과 동일 합니다. 이전 섹션에서 설명한 리소스 파일의 리소스 클래스에 속성으로 노출 됩니다.  
  
## <a name="example"></a>예제  
 이 예에서는 라는 문자열 리소스에는 폼의 제목을 설정 `Form1Title` 응용 프로그램 리소스 파일에서입니다. 이 예제에서 응용 프로그램 이라는 문자열 있어야 `Form1Title` 의 리소스 파일에 있습니다.  
  
 [!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>예제  
 이 예에서는 이라는 아이콘을 폼의 아이콘 설정 `Form1Icon` 응용 프로그램의 리소스 파일에 저장 된 합니다. 이 예제에서 응용 프로그램 이라는 아이콘이 있어야 `Form1Icon` 의 리소스 파일에 있습니다.  
  
 [!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>예제  
 명명 된 이미지 리소스를 폼의 배경 이미지를 설정 하는이 예제 `Form1Background`, 응용 프로그램 리소스 파일에 있습니다. 이 예제가 작동 하려면 응용 프로그램에 있어야 명명 된 이미지 리소스 `Form1Background` 의 리소스 파일에 있습니다.  
  
 [!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>예제  
 이 예제에서는 명명 된 오디오 리소스로 저장 된 소리를 재생 `Form1Greeting` 응용 프로그램의 리소스 파일에 있습니다. 이 예제에서 응용 프로그램 이라는 오디오 리소스가 있어야 `Form1Greeting` 의 리소스 파일에 있습니다. `My.Computer.Audio.Play` 메서드는 Windows Forms 응용 프로그램에 대해서만 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>예제  
 이 예제에서는 응용 프로그램의 문자열 리소스의 프랑스어 culture 버전을 검색 합니다. 리소스의 이름은 지정 `Message`합니다. Culture를 변경 하는 `My.Resources` 개체가 사용, 사용 하 여 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>합니다.  
  
 이 예제가 작동 하려면 응용 프로그램 이라는 문자열 있어야 `Message` 상대방이 리소스 파일과 응용 프로그램 없어야 Resources.fr-r e s x 해당 리소스 파일의 문화권 프랑스어 버전입니다. 응용 프로그램에 리소스 파일의 문화권 프랑스어 버전이 없는 경우는 `My.Resource` 개체는 기본 문화권 리소스 파일에서 리소스를 검색 합니다.  
  
 [!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 리소스 관리(.NET)](/visualstudio/ide/managing-application-resources-dotnet)  
 [데스크톱 앱의 리소스](../../../framework/resources/index.md)  

