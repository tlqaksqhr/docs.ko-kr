---
title: "방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거"
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
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce13ba3413c13ced7ff9a967e23d87622309feb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거
Windows Forms <xref:System.Windows.Forms.ImageList> 구성 요소가 일반적으로 이미지 되기 전에 채워집니다 컨트롤에 연결 됩니다. 그러나 추가 하 고는 컨트롤과 함께 이미지 목록을 연결한 후 이미지를 제거할 수 있습니다.  
  
> [!NOTE]
>  이미지를 제거 하면 확인 하 고 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 연결 된 컨트롤의 속성은 여전히 유효 합니다.  
  
### <a name="to-add-images-programmatically"></a>이미지를 추가 하려면 프로그래밍 방식으로  
  
-   사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 이미지 목록의 메서드 <xref:System.Windows.Forms.ImageList.Images%2A> 속성입니다.  
  
     다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 문서** 폴더입니다. Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더 포함 됩니다는 알 수 없으므로이 위치가 사용 됩니다. 이 위치를 선택에 사용자를 게 최소한의 시스템 액세스 수준이 더 안전 하 게 응용 프로그램을 실행할 수 있습니다. 다음 코드 예제에서는 포함 하는 폼이 있어야는 <xref:System.Windows.Forms.ImageList> 컨트롤이 이미 추가 합니다.  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a>키 값을 사용 하 여 이미지를 추가 합니다.  
  
-   중 하나를 사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 이미지 목록의 메서드 <xref:System.Windows.Forms.ImageList.Images%2A> 키 값을 사용 하는 속성입니다.  
  
     다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 문서** 폴더입니다. Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더 포함 됩니다는 알 수 없으므로이 위치가 사용 됩니다. 이 위치를 선택에 사용자를 게 최소한의 시스템 액세스 수준이 더 안전 하 게 응용 프로그램을 실행할 수 있습니다. 다음 코드 예제에서는 포함 하는 폼이 있어야는 <xref:System.Windows.Forms.ImageList> 컨트롤이 이미 추가 합니다.  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
1.  
  
### <a name="to-remove-all-images-programmatically"></a>모든 이미지를 프로그래밍 방식으로 제거 하려면  
  
-   사용 하 여 <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> 단일 이미지를 제거 하려면 메서드  
  
     -또는-  
  
     사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> 메서드는 이미지 목록에서 모든 이미지를 선택 취소 합니다.  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a>키로 이미지를 제거 하려면  
  
-   사용 된 <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> 메서드를 해당 키로 단일 이미지를 제거 합니다.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>참고 항목  
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [ImageList 구성 요소 개요](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
