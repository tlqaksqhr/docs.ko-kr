---
title: "컴퓨터 리소스에 액세스(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20c9d23570ec986598ad697f559aaf3a3153a8a0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="924d4-102">컴퓨터 리소스에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="924d4-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="924d4-103">`My.Computer` 개체는 `My`의 세 가지 중앙 개체 중 하나로, 이를 통해 정보 및 일반적으로 사용되는 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="924d4-104">`My.Computer`에서는 응용 프로그램이 실행되는 컴퓨터에 액세스하기 위한 메서드, 특성 및 이벤트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="924d4-105">다음과 같은 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-105">Its objects include:</span></span>  
  
-   <xref:Microsoft.VisualBasic.Devices.Audio>
-   <span data-ttu-id="924d4-106">클립보드(<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span><span class="sxs-lookup"><span data-stu-id="924d4-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
-   <xref:Microsoft.VisualBasic.Devices.Clock>
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem>
-   <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
-   <xref:Microsoft.VisualBasic.Devices.Keyboard>
-   <xref:Microsoft.VisualBasic.Devices.Mouse>
-   <xref:Microsoft.VisualBasic.Devices.Network>
-   <xref:Microsoft.VisualBasic.Devices.Ports>
-   <span data-ttu-id="924d4-107">레지스트리(<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span><span class="sxs-lookup"><span data-stu-id="924d4-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="924d4-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="924d4-108">In this section</span></span>

<span data-ttu-id="924d4-109">[소리 재생](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-109">[Playing Sounds](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span></span>  
<span data-ttu-id="924d4-110">백그라운드에서 소리를 재생하는 것과 같이 `My.Computer.Audio`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

<span data-ttu-id="924d4-111">[데이터를 클립보드에 저장하고 클립보드에서 읽기](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-111">[Storing Data to and Reading from the Clipboard](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span></span>  
<span data-ttu-id="924d4-112">클립보드에서 데이터를 읽거나 클립보드에 데이터를 쓰는 것과 같이 `My.Computer.Clipboard`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

<span data-ttu-id="924d4-113">[컴퓨터에 대한 정보 가져오기](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-113">[Getting Information about the Computer](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span></span>  
<span data-ttu-id="924d4-114">컴퓨터의 전체 이름 또는 IP 주소를 결정하는 것과 같이 `My.Computer.Info`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

<span data-ttu-id="924d4-115">[키보드에 액세스](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-115">[Accessing the Keyboard](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span></span>  
<span data-ttu-id="924d4-116">CAPS LOCK이 켜져 있는지 확인하는 것과 같이 `My.Computer.Keyboard`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

<span data-ttu-id="924d4-117">[마우스에 액세스](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-117">[Accessing the Mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span></span>  
<span data-ttu-id="924d4-118">마우스가 있는지 확인하는 것과 같이 `My.Computer.Mouse`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

<span data-ttu-id="924d4-119">[네트워크 작업 수행](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-119">[Performing Network Operations](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span></span>  
<span data-ttu-id="924d4-120">파일 업로드 또는 다운로드와 같이 `My.Computer.Network`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

<span data-ttu-id="924d4-121">[컴퓨터 포트에 액세스](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-121">[Accessing the Computer's Ports](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span></span>  
<span data-ttu-id="924d4-122">사용 가능한 직렬 포트를 표시하거나 직렬 포트에 문자열을 보내는 것과 같이 `My.Computer.Ports`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

<span data-ttu-id="924d4-123">[레지스트리 읽기 및 쓰기](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="924d4-123">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
<span data-ttu-id="924d4-124">레지스트리 키에서 데이터를 읽거나 레지스트리 키에 데이터를 쓰는 것과 같이 `My.Computer.Registry`와 연결된 작업을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="924d4-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
