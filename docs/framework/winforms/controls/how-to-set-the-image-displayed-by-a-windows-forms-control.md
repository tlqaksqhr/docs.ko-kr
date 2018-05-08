---
title: '방법: Windows Forms 컨트롤에서 표시하는 이미지 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 4870f9e2acc48a90e1e2193d514926fedee05f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>방법: Windows Forms 컨트롤에서 표시하는 이미지 설정
여러 Windows Forms 컨트롤 이미지를 표시할 수 있습니다. 이러한 이미지는 단추를 나타내는에 있는 디스켓 아이콘은 같은 컨트롤의 용도 설명 하는 아이콘이 있을 수 있습니다는 **저장** 명령입니다. 또는 아이콘 배경 이미지를 모양 및 원하는 동작을 제어 될 수 있습니다.  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>컨트롤에서 표시 되는 이미지를 설정 하려면  
  
1.  컨트롤의 `Image` 또는 `BackgroundImage` 속성 형식의 개체로 <xref:System.Drawing.Image>합니다. 일반적으로 로드 합니다 이미지 파일에서 사용 하 여는 <xref:System.Drawing.Image.FromFile%2A> 메서드.  
  
     다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 그림** 폴더입니다. 대부분의 Windows 운영 체제를 실행 중인 컴퓨터가이 디렉터리에 포함 됩니다. 그러면 상태도 안전 하 게 응용 프로그램을 실행 하려면 사용자는 최소한의 시스템 액세스 수준. 다음 코드 예제에서는 있어야 이미 포함 하는 폼을 <xref:System.Windows.Forms.PictureBox> 컨트롤을 추가 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
