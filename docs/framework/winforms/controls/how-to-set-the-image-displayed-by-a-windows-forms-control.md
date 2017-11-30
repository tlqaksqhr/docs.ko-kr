---
title: "방법: Windows Forms 컨트롤에서 표시하는 이미지 설정"
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
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6d9f4d806b39e6e1272ddbb60befdaf8c76e46b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="ac710-102">방법: Windows Forms 컨트롤에서 표시하는 이미지 설정</span><span class="sxs-lookup"><span data-stu-id="ac710-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="ac710-103">여러 Windows Forms 컨트롤 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="ac710-104">이러한 이미지는 단추를 나타내는에 있는 디스켓 아이콘은 같은 컨트롤의 용도 설명 하는 아이콘이 있을 수 있습니다는 **저장** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="ac710-105">또는 아이콘 배경 이미지를 모양 및 원하는 동작을 제어 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="ac710-106">컨트롤에서 표시 되는 이미지를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ac710-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="ac710-107">컨트롤의 `Image` 또는 `BackgroundImage` 속성 형식의 개체로 <xref:System.Drawing.Image>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="ac710-108">일반적으로 로드 합니다 이미지 파일에서 사용 하 여는 <xref:System.Drawing.Image.FromFile%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ac710-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="ac710-109">다음 코드 예제에서는 이미지의 위치 설정 된 경로 **내 그림** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="ac710-110">대부분의 Windows 운영 체제를 실행 중인 컴퓨터가이 디렉터리에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="ac710-111">그러면 상태도 안전 하 게 응용 프로그램을 실행 하려면 사용자는 최소한의 시스템 액세스 수준.</span><span class="sxs-lookup"><span data-stu-id="ac710-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="ac710-112">다음 코드 예제에서는 있어야 이미 포함 하는 폼을 <xref:System.Windows.Forms.PictureBox> 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac710-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac710-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac710-113">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
