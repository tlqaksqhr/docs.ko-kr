---
title: "연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 060f411dfc7c3153fdf0e0d6e19781f0d60b141b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize
사용자 지정 컨트롤 노출 하는 속성으로 컬렉션 경우도 있습니다. 이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 디자인 타임에 컬렉션을 serialize 하는 방법을 제어 하는 클래스입니다. 적용 된 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 컬렉션 속성에 값을 입력 하면 속성을 serialize 합니다.  
  
 단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: serialize 할 컬렉션의 표준 형식과 DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   충분 한 권한이을 만들고 Visual Studio가 설치 된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있습니다.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>직렬화 가능 컬렉션을 포함 하는 컨트롤 만들기  
 첫 번째 단계는 컨트롤을 속성으로 직렬화 가능 컬렉션을 만드는 것입니다. 사용 하 여이 컬렉션의 내용을 편집할 수는 **컬렉션 편집기**에서 액세스할 수 있는 **속성** 창.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>직렬화 가능 컬렉션을 사용 하 여 컨트롤을 만들려면  
  
1.  라는 Windows 컨트롤 라이브러리 프로젝트 만들기 `SerializationDemoControlLib`합니다. 자세한 내용은 참조 [Windows 컨트롤 라이브러리 템플릿](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4)합니다.  
  
2.  이름 바꾸기 `UserControl1` 를 `SerializationDemoControl`합니다. 자세한 내용은 참조 [하는 방법: 식별자 이름 바꾸기](http://msdn.microsoft.com/en-us/2430f732-2b70-4516-8cf6-a7bb71cc9724)합니다.  
  
3.  에 **속성** 창의 설정의 값은 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> 속성을 `10`합니다.  
  
4.  위치는 <xref:System.Windows.Forms.TextBox> 컨트롤에 `SerializationDemoControl`합니다.  
  
5.  <xref:System.Windows.Forms.TextBox> 컨트롤을 선택합니다. 에 **속성** 창에서 다음 속성을 설정 합니다.  
  
    |속성|다음으로 변경|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**도킹**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**스크롤 막대**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  에 **코드 편집기**, 라는 문자열 배열 필드를 선언 `stringsValue` 에서 `SerializationDemoControl`합니다.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  정의 `Strings` 속성에는 `SerializationDemoControl`합니다.  
  
> [!NOTE]
>  <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값 컬렉션의 serialization을 사용 하도록 설정 하는 데 사용 됩니다.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl 테스트 컨테이너**에서 컨트롤을 실행합니다.  
  
2.  찾을 `Strings` 속성에는 <xref:System.Windows.Forms.PropertyGrid> 의 **UserControl Test Container**합니다. 클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭은 **문자열컬렉션편집기**.  
  
3.  여러 문자열을 입력에서 **문자열 컬렉션 편집기**합니다. 각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다. 클릭 **확인** 문자열 입력 했으면 합니다.  
  
> [!NOTE]
>  입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.  
  
## <a name="serializing-a-collection-property"></a>컬렉션 속성을 직렬화합니다.  
 컨트롤의 serialization 동작을 테스트 하려면 폼에 배치를 사용 하 여 컬렉션의 내용을 변경 하는 **컬렉션 편집기**합니다. 특별 한 디자이너 파일을 확인 하 여 직렬화 된 컬렉션 상태를 볼 수는 **Windows Forms 디자이너** 에서 코드를 생성 합니다.  
  
#### <a name="to-serialize-a-collection"></a>컬렉션을 serialize 하는 데  
  
1.  Windows 응용 프로그램 프로젝트를 솔루션에 추가 합니다. 프로젝트 이름을 `SerializationDemoControlTest`로 지정합니다.  
  
2.  에 **도구 상자**, 이라는 탭 찾을 **SerializationDemoControlLib 구성 요소**합니다. 이 탭에서 찾을 수 있습니다는 `SerializationDemoControl`합니다. 자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하세요.  
  
3.  위치는 `SerializationDemoControl` 폼에 있습니다.  
  
4.  찾을 `Strings` 속성에는 **속성** 창. 클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭은 **문자열컬렉션편집기**.  
  
5.  여러 문자열을 입력에서 **문자열 컬렉션 편집기**합니다. 각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다. 클릭 **확인** 문자열 입력 했으면 합니다.  
  
> [!NOTE]
>  입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.  
  
1.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
2.  열기는 **Form1** 노드. 아래에 라는 파일을은 **form1. designer.cs** 또는 **Form1.Designer.vb**합니다. 이 파일을는 **Windows Forms 디자이너** 에서 폼과 해당 자식 컨트롤의 디자인 타임 상태를 나타내는 코드를 생성 합니다. **코드 편집기**에서 이 파일을 엽니다.  
  
3.  라는 영역을 열고 **Windows Form 디자이너에서 생성 한 코드** 라는 섹션을 찾아서 **serializationDemoControl1**합니다. 이 레이블은 아래에 컨트롤의 serialize 된 상태를 나타내는 코드입니다. 5 단계에서 입력 문자열에 대 한 할당에 표시 된 `Strings` 속성입니다. C# 및 Visual Basic의 경우 다음 코드 예제에서는 표시 되는 내용 문자열 "red", "주황색" 및 "노란색"를 입력 한 경우 유사한 코드를 표시 합니다.  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  에 **코드 편집기**의 값을 변경는 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 에 `Strings` 속성을 <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>합니다.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. 솔루션 및 3 및 4 단계를 반복 하 여 다시 작성 합니다.  
  
> [!NOTE]
>  이 경우에 **Windows Forms 디자이너** 에 대 한 할당을 내보내는 `Strings` 속성입니다.  
  
## <a name="next-steps"></a>다음 단계  
 표준 형식의 컬렉션을 serialize 하는 방법을 알게 되 면 디자인 타임 환경에 사용자 지정 컨트롤을 보다 강력 하 게 통합 하는 것이 좋습니다. 다음 항목에는 사용자 지정 컨트롤의 디자인 타임 통합 향상 하는 방법을 설명 합니다.  
  
-   [디자인 타임 아키텍처](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Serialization 디자이너 개요](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [Serialization 디자이너 개요](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [방법: designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 Serialize](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
