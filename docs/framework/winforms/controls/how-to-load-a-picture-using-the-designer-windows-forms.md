---
title: "방법: 디자이너를 사용하여 그림 로드(Windows Forms) | Microsoft Docs"
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
  - "폼, 이미지 표시"
  - "이미지[Windows Forms], Windows Forms에 표시"
  - "그림 형식"
  - "PictureBox 컨트롤[Windows Forms], 그림 추가"
  - "그림, 표시"
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 디자이너를 사용하여 그림 로드(Windows Forms)
Windows Forms <xref:System.Windows.Forms.PictureBox> 컨트롤을 사용하여 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 유효한 그림으로 설정하면 디자인 타임에서 그림을 폼에 로드하고 표시할 수 있습니다.  다음 표에서는 허용되는 파일 형식을 보여 줍니다.  
  
|형식|파일 확장명|  
|--------|------------|  
|비트맵|.bmp|  
|아이콘|.ico|  
|GIF|.gif|  
|메타파일|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에서 그림을 표시하려면  
  
1.  폼에 <xref:System.Windows.Forms.PictureBox> 컨트롤을 그립니다.  
  
2.  속성 창에서 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 선택한 다음 줄임표 단추를 클릭하여 **열기** 대화 상자를 표시합니다.  
  
3.  특정 파일 형식\(예: .gif 파일\)을 찾으려면 **파일 형식** 상자에서 해당 형식을 선택합니다.  
  
4.  표시할 파일을 선택합니다.  
  
### 디자인 타임에서 그림을 삭제하려면  
  
1.  **속성** 창에서 <xref:System.Windows.Forms.PictureBox.Image%2A> 속성을 선택한 다음 마우스 오른쪽 단추로 이미지 개체 이름의 왼쪽에 작게 표시된 축소판 이미지를 클릭합니다.  **다시 설정**을 선택합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.PictureBox>   
 [PictureBox 컨트롤 개요](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [방법: 런타임에 그림의 크기 또는 위치 수정](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [방법: 런타임에 그림 설정](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [PictureBox 컨트롤](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)