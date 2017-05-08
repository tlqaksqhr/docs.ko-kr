---
title: "방법: Windows Forms 컨트롤에서 표시하는 이미지 설정 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], 이미지"
  - "컨트롤[Windows Forms], 이미지"
  - "예제[Windows Forms], 컨트롤"
  - "이미지[Windows Forms], Windows Forms 컨트롤"
  - "Windows Forms 컨트롤, 이미지"
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms 컨트롤에서 표시하는 이미지 설정
몇몇 Windows Forms 컨트롤에서는 이미지를 표시할 수 있습니다.  단추의 디스켓 아이콘이 보통 **저장** 명령을 나타내는 것처럼 이러한 이미지는 컨트롤의 용도를 설명하는 아이콘이 될 수 있습니다.  또는 이 아이콘이 컨트롤에 원하는 모양과 동작을 제공하는 배경 이미지가 될 수 있습니다.  
  
### 컨트롤에 표시되는 이미지를 설정하려면  
  
1.  컨트롤의 `Image` 또는 `BackgroundImage` 속성을 <xref:System.Drawing.Image> 형식의 개체로 설정합니다.  일반적으로 <xref:System.Drawing.Image.FromFile%2A> 메서드를 사용하여 파일에서 이미지를 로드합니다.  
  
     다음 코드 예제에서 이미지의 위치로 설정된 경로는 **내 그림** 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에 이 디렉터리가 포함되어 있습니다.  또한 이 위치를 선택하면 사용자는 최소한의 시스템 액세스 수준으로 응용 프로그램을 안전하게 실행할 수 있습니다.  다음 코드 예제를 실행하려면 <xref:System.Windows.Forms.PictureBox> 컨트롤이 추가된 폼이 이미 있어야 합니다.  
  
    ```vb  
    ' Replace the image named below  
    ' with an icon of your own choosing.  
    PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.MyPictures) _  
       & "\Image.gif")  
  
    ```  
  
    ```csharp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.MyPictures)  
       + @"\Image.gif");  
  
    ```  
  
    ```cpp  
    // Replace the image named below  
    // with an icon of your own choosing.  
    pictureBox1->Image = Image::FromFile(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::MyPictures),  
       "\\Image.gif"));  
    ```  
  
## 참고 항목  
 <xref:System.Drawing.Image.FromFile%2A>   
 <xref:System.Drawing.Image>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>