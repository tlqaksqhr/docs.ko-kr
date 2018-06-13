---
title: Web Services Generics Serialization 기술 샘플
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 29cfa8f66f4b465d30c85c6944b8f3d94203f489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585618"
---
# <a name="web-services-generics-serialization-technology-sample"></a><span data-ttu-id="ae8b6-102">Web Services Generics Serialization 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="ae8b6-102">Web Services Generics Serialization Technology Sample</span></span>
[<span data-ttu-id="ae8b6-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="ae8b6-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 <span data-ttu-id="ae8b6-104">이 샘플에서는 ASP.NET 웹 서비스에서 제네릭의 serialization을 사용하고 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-104">This sample shows how to use and control the serialization of generics in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="ae8b6-105">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="ae8b6-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="ae8b6-106">Visual Studio를 열고 **파일** 메뉴에서 **새 웹 사이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-106">Open Visual Studio and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="ae8b6-107">**새 웹 사이트** 대화 상자의 왼쪽 창에서 원하는 프로그래밍 언어를 선택한 다음 오른쪽 창에서 **ASP.NET 웹 서비스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-107">In the **New Web Site** dialog, select from the left pane your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="ae8b6-108">**찾아보기**를 클릭하고 \CS\GenericsService 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-108">Click **Browse** and navigate to the \CS\GenericsService subdirectory.</span></span>  
  
4.  <span data-ttu-id="ae8b6-109">Service.asmx를 선택하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-109">Select Service.asmx to open the file in Visual Studio.</span></span>  
  
5.  <span data-ttu-id="ae8b6-110">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-110">On the **Build** menu, click **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae8b6-111">이 목록의 처음 5개 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-111">The first five steps in this list are optional.</span></span> <span data-ttu-id="ae8b6-112">.NET Framework 런타임에서는 웹 서비스가 처음 요청될 때 웹 서비스를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-112">The .NET Framework runtime will automatically generate the Web service the first time the service is requested.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae8b6-113">다음 단계는 샘플을 빌드하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-113">The following steps are required to build the sample.</span></span>  
  
1.  <span data-ttu-id="ae8b6-114">[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 \CS 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-114">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the \CS subdirectory.</span></span>  
  
2.  <span data-ttu-id="ae8b6-115">GenericsService 하위 디렉터리의 아이콘을 마우스 오른쪽 단추로 클릭하고 **공유 및 보안**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-115">Right-click the icon for the GenericsService subdirectory, and select **Sharing and Security**.</span></span>  
  
3.  <span data-ttu-id="ae8b6-116">**웹 공유** 탭에서 **이 폴더를 공유함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-116">In the **Web Sharing** tab, select **Share this Folder**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae8b6-117">샘플을 실행하는 데 필요하므로 **별칭** 창에 표시된 가상 디렉터리 이름을 기록해 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-117">Take note of the virtual directory name that is listed in the **Aliases** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-build-the-sample-using-internet-information-services"></a><span data-ttu-id="ae8b6-118">인터넷 정보 서비스를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="ae8b6-118">To build the sample using Internet Information Services</span></span>  
  
1.  <span data-ttu-id="ae8b6-119">**인터넷 정보 서비스** 관리 스냅인을 열고 **웹 사이트**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-119">Open the **Internet Information Services** management snap-in and expand **Web Sites**.</span></span>  
  
2.  <span data-ttu-id="ae8b6-120">**기본 웹 사이트**를 마우스 왼쪽 단추로 클릭하고 **새로 만들기**, **가상 디렉터리?** 를 차례로 선택하여 **가상 디렉터리 만들기 마법사**를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-120">Left-click **Default Web Site**, select **New**, and then select **Virtual Directory?** to create the **Virtual Directory Creation Wizard**.</span></span>  
  
3.  <span data-ttu-id="ae8b6-121">**다음**을 클릭하고 가상 디렉터리의 공용 별칭을 입력한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-121">Click **Next**, enter the public alias for your virtual directory, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="ae8b6-122">샘플을 저장한 디렉터리의 경로(일반적으로 \CS\GenericsService 하위 디렉터리)를 입력하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-122">Enter the path to the directory where you saved the sample (normally the \CS\GenericsService subdirectory) and click **Next**.</span></span> <span data-ttu-id="ae8b6-123">**다음**을 클릭하여 마법사를 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-123">Click **Next** to finish the wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae8b6-124">샘플을 실행하는 데 필요하므로 **별칭** 창에 표시된 가상 디렉터리 이름을 기록해 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-124">Take note of the virtual directory name that is listed in the **Alias** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="ae8b6-125">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ae8b6-125">To run the sample</span></span>  
  
1.  <span data-ttu-id="ae8b6-126">브라우저 창을 열고 주소 표시줄을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-126">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="ae8b6-127">형식  **http://localhost/[가상 directory]/Service.asmx**여기서 [가상 디렉터리] 샘플을 빌드할 때 만든 가상 디렉터리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-127">Type **http://localhost/[virtual directory]/Service.asmx**, where [virtual directory] represents the virtual directory you created when you built the sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae8b6-128">설명</span><span class="sxs-lookup"><span data-stu-id="ae8b6-128">Remarks</span></span>  
 <span data-ttu-id="ae8b6-129">이 샘플에서는 웹 서비스의 정의에 대한 링크가 포함된 기본 ASP.NET 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-129">The sample displays a default ASP.NET page that contains links to the definition of the Web Service.</span></span> <span data-ttu-id="ae8b6-130">웹 서비스의 소스 코드를 수정할 수 있을 뿐 아니라 화면 표시를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-130">You can customize the display in addition to modifying the source code for the Web service.</span></span> <span data-ttu-id="ae8b6-131">자세한 내용은 [XML Web Service 클라이언트 빌드](https://msdn.microsoft.com/library/c606f3cb-4111-45b4-ae42-9300420fa16c)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae8b6-131">For more information, see [Building XML Web Service Clients](https://msdn.microsoft.com/library/c606f3cb-4111-45b4-ae42-9300420fa16c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae8b6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae8b6-132">See Also</span></span>  
 <xref:System.Collections.Generic>  
 <xref:System.Web.Services>  
 <xref:System.Xml.Serialization>  
 [<span data-ttu-id="ae8b6-133">serialization</span><span class="sxs-lookup"><span data-stu-id="ae8b6-133">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="ae8b6-134">ASP.NET 및 XML Web Service 클라이언트를 사용하여 만든 XML Web Services</span><span class="sxs-lookup"><span data-stu-id="ae8b6-134">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)
