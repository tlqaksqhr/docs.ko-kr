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
ms.workload: dotnet
ms.openlocfilehash: 4e09448cb834453a4c8fce4494ab9fbb53eb0dc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="a46ca-102">방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="a46ca-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="a46ca-103">Windows Forms <xref:System.Windows.Forms.ImageList> 구성 요소가 일반적으로 이미지 되기 전에 채워집니다 컨트롤에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="a46ca-104">그러나 추가 하 고는 컨트롤과 함께 이미지 목록을 연결한 후 이미지를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a46ca-105">이미지를 제거 하면 확인 하 고 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 연결 된 컨트롤의 속성은 여전히 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="a46ca-106">이미지를 추가 하려면 프로그래밍 방식으로</span><span class="sxs-lookup"><span data-stu-id="a46ca-106">To add images programmatically</span></span>  
  
-   <span data-ttu-id="a46ca-107">사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 이미지 목록의 메서드 <xref:System.Windows.Forms.ImageList.Images%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="a46ca-108">다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a46ca-109">Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더 포함 됩니다는 알 수 없으므로이 위치가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a46ca-110">이 위치를 선택에 사용자를 게 최소한의 시스템 액세스 수준이 더 안전 하 게 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="a46ca-111">다음 코드 예제에서는 포함 하는 폼이 있어야는 <xref:System.Windows.Forms.ImageList> 컨트롤이 이미 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="a46ca-112">키 값을 사용 하 여 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-112">To add images with a key value.</span></span>  
  
-   <span data-ttu-id="a46ca-113">중 하나를 사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 이미지 목록의 메서드 <xref:System.Windows.Forms.ImageList.Images%2A> 키 값을 사용 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="a46ca-114">다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a46ca-115">Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더 포함 됩니다는 알 수 없으므로이 위치가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a46ca-116">이 위치를 선택에 사용자를 게 최소한의 시스템 액세스 수준이 더 안전 하 게 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="a46ca-117">다음 코드 예제에서는 포함 하는 폼이 있어야는 <xref:System.Windows.Forms.ImageList> 컨트롤이 이미 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="a46ca-118">모든 이미지를 프로그래밍 방식으로 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="a46ca-118">To remove all images programmatically</span></span>  
  
-   <span data-ttu-id="a46ca-119">사용 하 여 <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> 단일 이미지를 제거 하려면 메서드</span><span class="sxs-lookup"><span data-stu-id="a46ca-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="a46ca-120">-또는-</span><span class="sxs-lookup"><span data-stu-id="a46ca-120">,-or-</span></span>  
  
     <span data-ttu-id="a46ca-121">사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> 메서드는 이미지 목록에서 모든 이미지를 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="a46ca-122">키로 이미지를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="a46ca-122">To remove images by key</span></span>  
  
-   <span data-ttu-id="a46ca-123">사용 된 <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> 메서드를 해당 키로 단일 이미지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a46ca-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="a46ca-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a46ca-124">See Also</span></span>  
 [<span data-ttu-id="a46ca-125">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a46ca-125">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [<span data-ttu-id="a46ca-126">ImageList 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="a46ca-126">ImageList Component Overview</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [<span data-ttu-id="a46ca-127">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="a46ca-127">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
