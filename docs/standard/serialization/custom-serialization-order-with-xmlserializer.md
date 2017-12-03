---
title: "XmlSerializer를 통한 사용자 지정 Serialization 순서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e209cc0b016fe3bf0668463d9ccd3ee06784a25
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="b124c-102">XmlSerializer를 통한 사용자 지정 Serialization 순서</span><span class="sxs-lookup"><span data-stu-id="b124c-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="b124c-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="b124c-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="b124c-104">이 샘플에서는 XML serialization에서 serialize 및 deserialize되는 요소의 순서를 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="b124c-105">serialization에 대한 자세한 내용은 build.proj 파일 및 소스 코드의 주석을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b124c-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="b124c-106">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="b124c-106">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="b124c-107">명령 프롬프트 창을 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="b124c-108">명령줄에 **msbuild CustomOrder.sln**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="b124c-109">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="b124c-109">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="b124c-110">[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="b124c-111">CustomOrder.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="b124c-112">**빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="b124c-113">샘플 응용 프로그램이 기본 \bin 또는 \bin\Debug 하위 디렉터리에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b124c-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b124c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b124c-114">See Also</span></span>  
 [<span data-ttu-id="b124c-115">기본 serialization</span><span class="sxs-lookup"><span data-stu-id="b124c-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="b124c-116">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="b124c-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="b124c-117">특성을 사용하여 XML serialization 제어</span><span class="sxs-lookup"><span data-stu-id="b124c-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="b124c-118">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="b124c-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="b124c-119">serialization</span><span class="sxs-lookup"><span data-stu-id="b124c-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="b124c-120">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="b124c-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
