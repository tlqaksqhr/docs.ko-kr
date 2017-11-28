---
title: "방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
caps.latest.revision: "30"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea2e878ca4894612dda77075d04c924c3db8e293
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a><span data-ttu-id="6ea29-102">방법: .NET Framework 4.5 설치 관리자에서 진행률 가져오기</span><span class="sxs-lookup"><span data-stu-id="6ea29-102">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>
<span data-ttu-id="6ea29-103">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 재배포 가능 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-103">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is a redistributable runtime.</span></span> <span data-ttu-id="6ea29-104">.NET Framework의 이 버전용 응용 프로그램을 개발하는 경우 응용 프로그램 설치 시 필수 구성 요소로 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 포함(연결)시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-104">If you develop apps for this version of the .NET Framework, you can include (chain) [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup as a prerequisite part of your app's setup.</span></span> <span data-ttu-id="6ea29-105">사용자 지정 설치 환경이나 통합 설치 환경을 제공하려면 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로그램을 자동으로 시작하고 앱의 설치 진행률을 표시하는 동안 진행 상태를 추적하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-105">To present a customized or unified setup experience, you may want to silently launch [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup and track its progress while showing your app's setup progress.</span></span> <span data-ttu-id="6ea29-106">자동 추적을 사용하도록 설정하기 위해 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로그램(감시할 수 있음)은 메모리 매핑된 I/O(MMIO) 세그먼트를 사용하여 설치 프로그램과 함께 통신할 프로토콜(감시자 또는 chainer)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-106">To enable silent tracking, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup (which can be watched) defines a protocol by using a memory-mapped I/O (MMIO) segment to communicate with your setup (the watcher or chainer).</span></span> <span data-ttu-id="6ea29-107">이 프로토콜은 chainer가 진행률 정보를 가져오고, 자세한 결과를 확인하고. 메시지에 응답하고, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치를 취소하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-107">This protocol defines a way for a chainer to obtain progress information, get detailed results, respond to messages, and cancel the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup.</span></span>  
  
-   <span data-ttu-id="6ea29-108">**호출**.</span><span class="sxs-lookup"><span data-stu-id="6ea29-108">**Invocation** .</span></span>  <span data-ttu-id="6ea29-109">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로그램을 호출하고 MMIO 섹션에서 진행률 정보를 받으려면 설치 프로그램에서 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-109">To call [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup and receive progress information from the MMIO section, your setup program must do the following:</span></span>  
  
    1.  <span data-ttu-id="6ea29-110">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 프로그램을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-110">Call the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]redistributable program:</span></span>  
  
        ```  
        dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name  
        ```  
  
         <span data-ttu-id="6ea29-111">여기서 *section name*은 응용 프로그램을 식별하는 데 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-111">where *section name* is any name you want to use to identify your app.</span></span> <span data-ttu-id="6ea29-112">.NET Framework 설치 프로그램은 MMIO 섹션을 읽고 비동기적으로 쓰므로 이 시간 동안 이벤트 및 메시지를 사용하는 것이 편리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-112">.NET Framework setup reads and writes to the MMIO section asynchronously, so you might find it convenient to use events and messages during that time.</span></span> <span data-ttu-id="6ea29-113">예제에서는 MMIO 섹션(`TheSectionName`)을 할당하고 이벤트(`TheEventName`)를 정의하는 생성자가 .NET Framework 설치 프로세스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-113">In the example, the .NET Framework setup process is created by a constructor that both allocates the MMIO section (`TheSectionName`) and defines an event (`TheEventName`):</span></span>  
  
        ```  
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")  
        ```  
  
         <span data-ttu-id="6ea29-114">이러한 이름을 설치 프로그램에 고유한 이름으로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="6ea29-114">Please replace those names with names that are unique to your setup program.</span></span>  
  
    2.  <span data-ttu-id="6ea29-115">MMIO 섹션을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-115">Read from the MMIO section.</span></span> <span data-ttu-id="6ea29-116">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 다운로드 및 설치 작업은 동시에 진행됩니다. 따라서 .NET Framework에서 하나의 구성 요소를 설치하면서 다른 구성 요소를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-116">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the download and installation operations are simultaneous: One part of the .NET Framework might be installing while another part is downloading.</span></span> <span data-ttu-id="6ea29-117">따라서 진행률이 0에서 255까지 증가하는 두 개의 숫자(`m_downloadSoFar` 및 `m_installSoFar`)로 MMIO 섹션에 다시 전송(기록)됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-117">As a result, progress is sent back (that is, written) to the MMIO section as two numbers (`m_downloadSoFar` and `m_installSoFar`) that increase from 0 to 255.</span></span> <span data-ttu-id="6ea29-118">255가 기록되고 .NET Framework가 종료되면 설치가 완료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-118">When 255 is written and the .NET Framework exits, the installation is complete.</span></span>  
  
-   <span data-ttu-id="6ea29-119">**종료 코드**.</span><span class="sxs-lookup"><span data-stu-id="6ea29-119">**Exit codes**.</span></span> <span data-ttu-id="6ea29-120">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 프로그램을 호출하는 명령의 다음 종료 코드는 설치에 성공했는지 아니면 실패했는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-120">The following exit codes from the command to call the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable program indicate whether setup has succeeded or failed:</span></span>  
  
    -   <span data-ttu-id="6ea29-121">0 - 설치가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-121">0 - Setup completed successfully.</span></span>  
  
    -   <span data-ttu-id="6ea29-122">3010 – 설치가 완료되었습니다. 시스템 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-122">3010 – Setup completed successfully; a system restart is required.</span></span>  
  
    -   <span data-ttu-id="6ea29-123">1602 – 설치가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-123">1602 – Setup has been canceled.</span></span>  
  
    -   <span data-ttu-id="6ea29-124">기타 모든 코드 - 설치 중 오류가 발생했습니다. 자세한 내용을 보려면 %temp%에 생성된 로그 파일을 검사하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea29-124">All other codes - Setup encountered errors; examine the log files created in %temp% for details.</span></span>  
  
-   <span data-ttu-id="6ea29-125">**설치 취소**.</span><span class="sxs-lookup"><span data-stu-id="6ea29-125">**Canceling setup**.</span></span> <span data-ttu-id="6ea29-126">언제든지 `Abort` 메서드를 통해 MMIO 섹션에 `m_downloadAbort` 및 `m_ installAbort` 플래그를 설정하여 설치를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-126">You can cancel setup at any time by using the `Abort` method to set the `m_downloadAbort` and `m_ installAbort` flags in the MMIO section.</span></span>  
  
## <a name="chainer-sample"></a><span data-ttu-id="6ea29-127">chainer 샘플</span><span class="sxs-lookup"><span data-stu-id="6ea29-127">Chainer Sample</span></span>  
 <span data-ttu-id="6ea29-128">chainer 샘플은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 프로그램을 자동으로 시작하고 진행률을 표시하는 동안 설치를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-128">The Chainer sample silently launches and tracks [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup while showing progress.</span></span> <span data-ttu-id="6ea29-129">이 샘플은 .NET Framework 4에 대해 제공된 chainer 샘플과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-129">This sample is similar to the Chainer sample provided for the .NET Framework 4.</span></span> <span data-ttu-id="6ea29-130">그러나 또한 .NET Framework 4 앱을 닫기 위한 메시지 상자를 처리하여 시스템 다시 시작을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-130">However, in addition, it can avoid system restarts by processing the message box for closing .NET Framework 4 apps.</span></span> <span data-ttu-id="6ea29-131">이 메시지 상자에 대한 자세한 내용은 [.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기](../../../docs/framework/deployment/reducing-system-restarts.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea29-131">For information about this message box, see [Reducing System Restarts During .NET Framework 4.5 Installations](../../../docs/framework/deployment/reducing-system-restarts.md).</span></span> <span data-ttu-id="6ea29-132">.NET Framework 4 설치 관리자와 함께 이 샘플을 사용할 수 있습니다. 해당 시나리오에서는 메시지가 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-132">You can use this sample with the .NET Framework 4 installer; in that scenario, the message is simply not sent.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6ea29-133">관리자 권한으로 예제를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-133">You must run the example as an administrator.</span></span>  
  
 <span data-ttu-id="6ea29-134">MSDN 샘플 갤러리에서 [.NET Framework 4.5 chainer 샘플](http://go.microsoft.com/fwlink/?LinkId=231345)에 대한 전체 Visual Studio 솔루션을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-134">You can download the complete Visual Studio solution for the [.NET Framework 4.5 Chainer Sample](http://go.microsoft.com/fwlink/?LinkId=231345) from the MSDN Samples Gallery.</span></span>  
  
 <span data-ttu-id="6ea29-135">다음 섹션에서는 이 샘플의 중요한 파일인 MMIOChainer.h, ChainingdotNet4.cpp 및 IProgressObserver.h에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-135">The following sections describe the significant files in this sample: MMIOChainer.h, ChainingdotNet4.cpp, and IProgressObserver.h.</span></span>  
  
#### <a name="mmiochainerh"></a><span data-ttu-id="6ea29-136">MMIOChainer.h</span><span class="sxs-lookup"><span data-stu-id="6ea29-136">MMIOChainer.h</span></span>  
  
-   <span data-ttu-id="6ea29-137">MMIOChainer.h 파일([전체 코드](http://go.microsoft.com/fwlink/?LinkId=231369) 참조)에는 chainer 클래스가 파생되어야 하는 데이터 구조 정의와 기본 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-137">The MMIOChainer.h file (see [complete code](http://go.microsoft.com/fwlink/?LinkId=231369)) contains the data structure definition and the base class from which the chainer class should be derived.</span></span> <span data-ttu-id="6ea29-138">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 MMIO 데이터 구조를 확장하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 설치 관리자에 필요한 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-138">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] extends the MMIO data structure to handle data that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] installer needs.</span></span> <span data-ttu-id="6ea29-139">MMIO 구조에 대한 변경 내용은 이전 버전과 호환되므로 .NET Framework 4 chainer가 다시 컴파일하지 않고도 .NET Framework 4.5 설치 프로그램에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-139">The changes to the MMIO structure are backward-compatible, so a .NET Framework 4 chainer can work with .NET Framework 4.5 setup without requiring recompilation.</span></span> <span data-ttu-id="6ea29-140">그러나 이 시나리오에서는 시스템 다시 시작을 줄이는 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-140">However, this scenario does not support the feature for reducing system restarts.</span></span>  
  
     <span data-ttu-id="6ea29-141">버전 필드를 통해 구조 및 메시지 형식에 대한 수정 버전을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-141">A version field provides a means of identifying revisions to the structure and message format.</span></span>  <span data-ttu-id="6ea29-142">.NET Framework 설치 프로그램은 `VirtualQuery` 함수 호출을 통해 파일 매핑의 크기를 확인하여 chainer 인터페이스 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-142">The .NET Framework setup determines the version of the chainer interface by calling the `VirtualQuery` function to determine the size of the file mapping.</span></span>  <span data-ttu-id="6ea29-143">크기가 버전 필드를 수용하기에 충분히 큰 경우 .NET Framework 설치 프로그램은 지정된 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-143">If the size is large enough to accommodate the version field, .NET Framework setup uses the specified value.</span></span> <span data-ttu-id="6ea29-144">.NET Framework 4의 경우처럼 파일 매핑이 너무 작아서 버전 필드를 포함할 수 없는 경우 설치 프로세스에서 버전 0(4)을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-144">If the file mapping is too small to contain a version field, which is the case with the .NET Framework 4, the setup process assumes version 0 (4).</span></span> <span data-ttu-id="6ea29-145">chainer가 .NET Framework 설치 프로그램에서 보내려고 하는 메시지 버전을 지원하지 않는 경우 .NET Framework 설치 프로그램은 무시 응답을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-145">If the chainer does not support the version of the message that .NET Framework setup wants to send, .NET Framework setup assumes an ignore response.</span></span>  
  
     <span data-ttu-id="6ea29-146">MMIO 데이터 구조는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-146">The MMIO data structure is defined as follows:</span></span>  
  
    ```cpp  
    // MMIO data structure for interprocess communication  
        struct MmioDataStructure  
        {  
            bool m_downloadFinished;               // Is download complete?  
            bool m_installFinished;                // Is installation complete?  
            bool m_downloadAbort;                  // Set to cause downloader to abort.  
            bool m_installAbort;                   // Set to cause installer to abort.  
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.  
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.  
            HRESULT m_hrInternalError;  
            WCHAR m_szCurrentItemStep[MAX_PATH];  
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).   
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).  
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.  
  
            BYTE m_version;                        // Version of the data structure, set by chainer:  
                                                   // 0x0: .NET Framework 4   
                                                   // 0x1: .NET Framework 4.5  
  
            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.  
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.  
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.  
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.  
        };  
    ```  
  
-   <span data-ttu-id="6ea29-147">`MmioDataStructure` 데이터 구조를 직접 사용하면 안 됩니다. `MmioChainer` 클래스를 대신 사용하여 chainer를 구현하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea29-147">The `MmioDataStructure` data structure should not be used directly; use the `MmioChainer` class instead to implement your chainer.</span></span> <span data-ttu-id="6ea29-148">`MmioChainer` 클래스에서 파생하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 패키지를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-148">Derive from the `MmioChainer` class to chain the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable.</span></span>  
  
#### <a name="iprogressobserverh"></a><span data-ttu-id="6ea29-149">IProgressObserver.h</span><span class="sxs-lookup"><span data-stu-id="6ea29-149">IProgressObserver.h</span></span>  
  
-   <span data-ttu-id="6ea29-150">IProgressObserver.h 파일은 진행률 관찰자([전체 코드 참조](http://go.microsoft.com/fwlink/?LinkId=231370))를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-150">The IProgressObserver.h file implements a progress observer ([see complete code](http://go.microsoft.com/fwlink/?LinkId=231370)).</span></span> <span data-ttu-id="6ea29-151">이 관찰자는 다운로드 및 설치 진행률에 대한 알림을 받습니다(부호 없는 `char` 0-255로 지정됨, 1%-100% 완료를 나타냄).</span><span class="sxs-lookup"><span data-stu-id="6ea29-151">This observer gets notified of download and installation progress (specified as an unsigned `char`, 0-255, indicating 1%-100% complete).</span></span> <span data-ttu-id="6ea29-152">chainee가 메시지를 보낼 때도 관찰자에게 알림이 전달되며, 관찰자는 응답을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-152">The observer is also notified when the chainee sends a message, and the observer should send a response.</span></span>  
  
    ```cpp  
        class IProgressObserver  
        {  
        public:  
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%  
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete    
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent  
        };  
    ```  
  
#### <a name="chainingdotnet45cpp"></a><span data-ttu-id="6ea29-153">ChainingdotNet4.5.cpp</span><span class="sxs-lookup"><span data-stu-id="6ea29-153">ChainingdotNet4.5.cpp</span></span>  
  
-   <span data-ttu-id="6ea29-154">[ChainingdotNet4.5.cpp](http://go.microsoft.com/fwlink/?LinkId=231368) 파일은 `MmioChainer` 클래스에서 파생되는 `Server` 클래스를 구현하고 진행률 정보를 표시하기 위해 적절한 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-154">The [ChainingdotNet4.5.cpp](http://go.microsoft.com/fwlink/?LinkId=231368) file implements the `Server` class, which derives from the `MmioChainer` class and overrides the appropriate methods to display progress information.</span></span> <span data-ttu-id="6ea29-155">MmioChainer는 지정된 섹션 이름으로 섹션을 만들고 지정된 이벤트 이름으로 chainer를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-155">The MmioChainer creates a section with the specified section name and initializes the chainer with the specified event name.</span></span> <span data-ttu-id="6ea29-156">이벤트 이름은 매핑된 데이터 구조에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-156">The event name is saved in the mapped data structure.</span></span> <span data-ttu-id="6ea29-157">섹션 및 이벤트 이름을 고유하게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-157">You should make the section and event names unique.</span></span> <span data-ttu-id="6ea29-158">다음 코드의 `Server` 클래스는 지정된 설치 프로그램을 시작하고 해당 진행률을 모니터링하고 종료 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-158">The `Server` class in the following code launches the specified setup program, monitors its progress, and returns an exit code.</span></span>  
  
    ```cpp  
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver  
    {  
    public:  
        …………….  
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names  
        {}  
    ```  
  
     <span data-ttu-id="6ea29-159">Main 메서드에서 설치가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-159">The installation is started in the Main method.</span></span>  
  
    ```cpp  
    // Main entry point for program  
    int __cdecl main(int argc, _In_count_(argc) char **_argv)  
    {  
        int result = 0;  
        CString args;  
        if (argc > 1)  
        {  
            args = CString(_argv[1]);  
        }  
  
        if (IsNetFx4Present(NETFX45_RC_REVISION))  
        {  
            printf(".NET Framework 4.5 is already installed");  
        }  
        else  
        {  
            result = Server().Launch(args);  
        }  
  
        return result;  
    }  
    ```  
  
-   <span data-ttu-id="6ea29-160">설치를 시작하기 전에 chainer는 `IsNetFx4Present`를 호출하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 이미 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-160">Before launching the installation, the chainer checks to see if the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is already installed by calling `IsNetFx4Present`:</span></span>  
  
    ```cpp  
    ///  Checks for presence of the .NET Framework 4.  
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full  
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.  
    #define NETFX40_FULL_REVISION 0  
    // TODO: Replace with released revision number  
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5   
    bool IsNetFx4Present(DWORD dwMinimumRelease)  
    {  
        DWORD dwError = ERROR_SUCCESS;  
        HKEY hKey = NULL;  
        DWORD dwData = 0;  
        DWORD dwType = 0;  
        DWORD dwSize = sizeof(dwData);  
  
        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);  
        if (ERROR_SUCCESS == dwError)  
        {  
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);  
  
            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))  
            {  
                dwError = ERROR_INVALID_DATA;  
            }  
            else if (ERROR_FILE_NOT_FOUND == dwError)  
            {  
                // Release value was not found, let's check for 4.0.  
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);  
  
                // Install = (REG_DWORD)1;  
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))  
                {  
                    // treat 4.0 as Release = 0  
                    dwData = 0;  
                }  
                else  
                {  
                    dwError = ERROR_INVALID_DATA;  
                }  
            }  
        }  
  
        if (hKey != NULL)  
        {  
            ::RegCloseKey(hKey);  
        }  
  
        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));  
    }  
    ```  
  
-   <span data-ttu-id="6ea29-161">올바른 위치를 가리키도록 `Launch` 메서드의 실행 파일(예제에서는 Setup.exe) 경로를 변경하거나 코드를 사용자 지정하여 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-161">You can change the path of the executable (Setup.exe in the example) in the `Launch` method to point to its correct location, or customize the code to determine the location.</span></span> <span data-ttu-id="6ea29-162">`MmioChainer` 기본 클래스는 파생 클래스가 호출하는 차단 `Run()` 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-162">The `MmioChainer` base class provides a blocking `Run()` method that the derived class calls.</span></span>  
  
    ```cpp  
    bool Launch(const CString& args)  
    {  
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run  
    STARTUPINFO si = {0};  
    si.cb = sizeof(si);  
    PROCESS_INFORMATION pi = {0};  
  
    // Launch the Setup.exe that installs the .NET Framework 4.5  
    BOOL bLaunchedSetup = ::CreateProcess(NULL,   
     cmdline.GetBuffer(),  
     NULL, NULL, FALSE, 0, NULL, NULL,   
     &si,  
     &pi);  
  
    // If successful   
    if (bLaunchedSetup != 0)  
    {  
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);  
    Run(pi.hProcess, observer);  
  
    ……………………..   
    return (bLaunchedSetup != 0);  
    }  
    ```  
  
-   <span data-ttu-id="6ea29-163">`Send` 메서드는 메시지를 가로채서 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-163">The `Send` method intercepts and processes the messages.</span></span>  <span data-ttu-id="6ea29-164">이 버전의 .NET Framework에서 지원되는 메시지는 응용 프로그램 닫기 메시지뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-164">In this version of the .NET Framework, the only supported message is the close application message.</span></span>  
  
    ```cpp  
            // SendMessage  
            //  
            // Send a message and wait for the response.  
            // dwMessage: Message to send  
            // pData: The buffer to copy the data to  
            // dwDataLength: Initially a pointer to the size of pBuffer.  Upon successful call, the number of bytes copied to pBuffer.  
            //--------------------------------------------------------------  
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)  
        {  
            DWORD dwResult = 0;  
            printf("recieved message: %d\n", dwMessage);  
            // Handle message  
            switch (dwMessage)  
            {  
            case MMIO_CLOSE_APPS:  
                {  
                    printf("    applications are holding files in use:\n");  
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);  
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)  
                    {  
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);  
                    }  
  
                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");  
                    while (dwResult == 0)  
                    {  
                        switch (toupper(getwchar()))  
                        {  
                        case 'Y':  
                            dwResult = IDYES;  // Close apps  
                            break;  
                        case 'N':  
                            dwResult = IDNO;  
                            break;  
                        case 'R':  
                            dwResult = IDRETRY;  
                            break;  
                        }  
                    }  
                    printf("\n");  
                    break;  
                }  
            default:  
                break;  
            }  
            printf("  response: %d\n  ", dwResult);  
            return dwResult;  
        }  
    };  
    ```  
  
-   <span data-ttu-id="6ea29-165">진행률 데이터는 0(0%)에서 255(100%) 사이의 부호 없는 `char`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-165">Progress data is an unsigned `char` between 0 (0%) and 255 (100%).</span></span>  
  
    ```cpp  
    private: // IProgressObserver  
        virtual void OnProgress(unsigned char ubProgressSoFar)  
        {…………  
       }  
    ```  
  
-   <span data-ttu-id="6ea29-166">HRESULT는 `Finished` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-166">The HRESULT is passed to the `Finished` method.</span></span>  
  
    ```cpp  
    virtual void Finished(HRESULT hr)  
    {  
    // This HRESULT is communicated over MMIO and may be different than process  
    // Exit code of the Chainee Setup.exe itself  
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);  
    }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6ea29-167">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 재배포 가능 패키지는 일반적으로 많은 진행률 메시지와 완료를 나타내는 단일 메시지(chainer 쪽)를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-167">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable typically writes many progress messages and a single message that indicates completion (on the chainer side).</span></span> <span data-ttu-id="6ea29-168">또한 비동기적으로 읽으면서 `Abort` 레코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-168">It also reads asynchronously, looking for `Abort` records.</span></span> <span data-ttu-id="6ea29-169">`Abort` 레코드를 받으면 설치를 취소하고, 설치가 중단되고 설치 작업이 롤백된 후 E_ABORT를 해당 데이터로 사용하여 완성된 레코드를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-169">If it receives an `Abort` record, it cancels the installation, and writes a finished record with E_ABORT as its data after the installation has been aborted and setup operations have been rolled back.</span></span>  
  
 <span data-ttu-id="6ea29-170">일반적인 서버는 임의의 MMIO 파일 이름을 만들고, 파일을 만든 다음(이전 코드 예제와 같이 `Server::CreateSection`에서) `CreateProcess` 메서드를 사용하고 `-pipe someFileSectionName` 옵션으로 파이프 이름을 전달하여 재배포 가능 패키지를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-170">A typical server creates a random MMIO file name, creates the file (as shown in the previous code example, in `Server::CreateSection`), and launches the redistributable by using the `CreateProcess` method and passing the pipe name with the `-pipe someFileSectionName` option.</span></span> <span data-ttu-id="6ea29-171">서버는 응용 프로그램 UI 관련 코드를 사용하여 `OnProgress`, `Send` 및 `Finished` 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea29-171">The server should implement `OnProgress`, `Send`, and `Finished` methods with application UI-specific code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea29-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ea29-172">See Also</span></span>  
 [<span data-ttu-id="6ea29-173">개발자를 위한 배포 가이드</span><span class="sxs-lookup"><span data-stu-id="6ea29-173">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [<span data-ttu-id="6ea29-174">배포</span><span class="sxs-lookup"><span data-stu-id="6ea29-174">Deployment</span></span>](../../../docs/framework/deployment/index.md)
