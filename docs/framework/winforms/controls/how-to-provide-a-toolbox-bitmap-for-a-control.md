---
title: "방법: 컨트롤에 대한 도구 상자 비트맵 제공 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "비트맵[Windows Forms], 사용자 지정 컨트롤"
  - "사용자 지정 컨트롤[Windows Forms], 도구 상자 비트맵"
  - "도구 상자[Windows Forms], 사용자 지정 컨트롤에 대한 비트맵 추가"
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 방법: 컨트롤에 대한 도구 상자 비트맵 제공
**도구 상자**에 표시되는 컨트롤에 특수 아이콘을 사용하려면 <xref:System.Drawing.ToolboxBitmapAttribute>를 사용하여 특정 이미지를 지정합니다.  이 클래스는 다른 클래스에 연결할 수 있는 특수 클래스인 *특성*입니다.  특성에 대한 자세한 내용은 [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/ko-kr/0d0cff64-892d-4f57-83bd-bef388553d4f)\([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) 및 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)\([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\)를 참조하십시오.  
  
 <xref:System.Drawing.ToolboxBitmapAttribute>를 사용하여 16x16 픽셀 비트맵의 경로 및 파일 이름을 나타내는 문자열을 지정할 수 있습니다.  그러면 컨트롤을 **도구 상자**에 추가할 때 컨트롤 옆에 이 비트맵이 나타납니다.  특정 형식과 연결된 비트맵이 로드되도록 <xref:System.Type>을 지정할 수도 있습니다.  <xref:System.Type>과 문자열을 모두 지정하면 컨트롤에서는 <xref:System.Type> 매개 변수로 지정된 형식이 포함된 어셈블리에서 문자열 매개 변수로 지정된 이름을 가진 이미지 리소스를 검색합니다.  
  
### 컨트롤을 위한 도구 상자 비트맵을 지정하려면  
  
1.  <xref:System.Drawing.ToolboxBitmapAttribute>를 컨트롤의 클래스 선언에 추가합니다. [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서는 `Class` 키워드 앞에 추가하고 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서는 클래스 선언 위쪽에 추가합니다.  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  프로젝트를 다시 빌드합니다.  
  
    > [!NOTE]
    >  비트맵은 자동 생성된 컨트롤 및 구성 요소의 도구 상자에는 나타나지 않습니다.  비트맵을 보려면 **도구 상자 항목 선택** 대화 상자를 사용하여 컨트롤을 다시 로드합니다.  자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Drawing.ToolboxBitmapAttribute>   
 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [디자인할 때 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Attributes](../Topic/Attributes%20\(Visual%20Basic\)1.md)   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)