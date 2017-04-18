---
title: "방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거 | Microsoft Docs"
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
  - "ImageList 구성 요소[Windows Forms], 이미지 추가"
  - "ImageList 구성 요소[Windows Forms], 이미지 제거"
  - "이미지[Windows Forms], ImageList 구성 요소에 추가"
  - "이미지[Windows Forms], 컨트롤을 사용하여 표시"
  - "이미지[Windows Forms], ImageList 구성 요소에서 제거"
  - "이미지[Windows Forms], 컨트롤에 대해 저장"
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거
Windows Forms <xref:System.Windows.Forms.ImageList> 구성 요소는 일반적으로 컨트롤과 연결하기 전에 이미지로 채워집니다.  그러나 이미지 목록을 컨트롤과 연결한 후에도 이미지를 추가하거나 제거할 수 있습니다.  
  
> [!NOTE]
>  컨트롤에서 이미지를 제거하는 경우에는 연결된 컨트롤의 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 속성이 계속 유효한지 확인합니다.  
  
### 프로그래밍 방식으로 이미지를 추가하려면  
  
-   이미지 목록에 있는 <xref:System.Windows.Forms.ImageList.Images%2A> 속성의 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 메서드를 사용합니다.  
  
     다음 코드 예제에서 이미지의 위치로 설정된 경로는 **내 문서** 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서 폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 내 문서 폴더를 선택하면 사용자는 최소한의 시스템 액세스 수준을 갖고 응용 프로그램을 안전하게 실행할 수 있습니다.  다음 코드 예제를 실행하려면 <xref:System.Windows.Forms.ImageList> 컨트롤이 추가된 폼이 이미 있어야 합니다.  
  
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
  
### 키 값으로 이미지를 추가하려면  
  
-   키 값을 받는 이미지 목록의 <xref:System.Windows.Forms.ImageList.Images%2A> 속성의 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 메서드 중 하나를 사용합니다.  
  
     다음 코드 예제에서 이미지의 위치로 설정된 경로는 **내 문서** 폴더입니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서 폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 내 문서 폴더를 선택하면 사용자는 최소한의 시스템 액세스 수준을 갖고 응용 프로그램을 안전하게 실행할 수 있습니다.  다음 코드 예제를 실행하려면 <xref:System.Windows.Forms.ImageList> 컨트롤이 추가된 폼이 이미 있어야 합니다.  
  
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
  
### 프로그래밍 방식으로 모든 이미지를 제거하려면  
  
-   단일 이미지를 제거하려면 <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> 메서드를 사용합니다.  
  
     \-또는\-  
  
     이미지 목록의 모든 이미지를 지우려면 <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> 메서드를 사용합니다.  
  
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
  
### 키로 이미지를 제거하려면  
  
-   키로 단일 이미지를 제거하려면 <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> 메서드를 사용합니다.  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
  
```  
  
## 참고 항목  
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)   
 [ImageList 구성 요소 개요](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)   
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)