---
title: "Web Services IXmlSerializable 기술 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0202d3f1-a50b-427d-a5bb-79208b8f1c22
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 72c7e9e1cbf47dd54726a16ddeb58a193d62dc31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="web-services-ixmlserializable-technology-sample"></a><span data-ttu-id="c35e3-102">Web Services IXmlSerializable 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="c35e3-102">Web Services IXmlSerializable Technology Sample</span></span>
[<span data-ttu-id="c35e3-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="c35e3-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/IXmlSerializable.zip.exe)  
  
 <span data-ttu-id="c35e3-104">이 샘플에서는 <xref:System.Xml.Serialization.IXmlSerializable>을 사용하여 ASP.NET 웹 서비스에서 사용자 지정 형식의 serialization을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-104">This sample shows how to use <xref:System.Xml.Serialization.IXmlSerializable> to control the serialization of custom types in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="c35e3-105">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="c35e3-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="c35e3-106">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 열고 **파일** 메뉴에서 **새 웹 사이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-106">Open [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="c35e3-107">**새 웹 사이트** 대화 상자의 왼쪽 창에서 원하는 프로그래밍 언어를 선택한 다음 오른쪽 창에서 **ASP.NET 웹 서비스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-107">In the left pane of the **New Web Site** dialog, select your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="c35e3-108">새 웹 서비스의 이름으로 **IXmlSerializable**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-108">Type **IXmlSerializable** as the name of the new Web service.</span></span>  
  
4.  <span data-ttu-id="c35e3-109">솔루션 탐색기 창에서 Service.asmx의 아이콘을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택한 다음, Service.asmx의 코드 숨김 파일에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-109">In the Solution Explorer window, right-click the icon for Service.asmx and select **Delete**; repeat this step for the Service.asmx codebehind file.</span></span>  
  
5.  <span data-ttu-id="c35e3-110">프로젝트 디렉터리를 마우스 오른쪽 단추로 클릭하고 **기존 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-110">Right-click the project directory and select **Add Existing Item**.</span></span> <span data-ttu-id="c35e3-111">대화 상자에서 언어별 디렉터리의 Service 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-111">In the dialog, navigate to the Service subdirectory of the language-specific directory.</span></span>  
  
6.  <span data-ttu-id="c35e3-112">Service.asmx를 선택한 다음 Service.asmx 코드 숨김 파일에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-112">Select Service.asmx, then repeat this step for the Service.asmx codebehind file.</span></span>  
  
7.  <span data-ttu-id="c35e3-113">[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 위의 3단계에서 만든 IXmlSerializable 디렉터리가 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-113">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the directory that contains IXmlSerializable directory that you created in step 3 above.</span></span>  
  
8.  <span data-ttu-id="c35e3-114">IXmlSerializable 디렉터리의 아이콘을 마우스 오른쪽 단추로 클릭하고 **공유 및 보안**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-114">Right-click the icon for the IXmlSerializable directory and select **Sharing and Security**.</span></span>  
  
9. <span data-ttu-id="c35e3-115">웹 공유 탭에서 **이 폴더를 공유함**을 선택하고 IXmlSerializable이라는 이름을 비롯한 기본 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-115">In the Web Sharing tab, select **Share this Folder**, and confirm the default settings, including the name IXmlSerializable.</span></span>  
  
10. <span data-ttu-id="c35e3-116">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-116">Click **OK**.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="c35e3-117">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c35e3-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="c35e3-118">브라우저 창을 열고 주소 표시줄을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-118">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="c35e3-119">**http://localhost/IXmlSerializable/Service.asmx**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c35e3-119">Type **http://localhost/IXmlSerializable/Service.asmx**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35e3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c35e3-120">See Also</span></span>  
 <xref:System.Xml.Serialization.IXmlSerializable>  
 <xref:System.Xml.Serialization>  
 <xref:System.Xml.XmlConvert>  
 <xref:System.Xml.XmlQualifiedName>  
 <xref:System.Xml.XmlReader>  
 <xref:System.Xml.Schema.XmlSchema>  
 <xref:System.Xml.Schema.XmlSchemaSet>  
 <xref:System.Xml.XmlUrlResolver>  
 <xref:System.Xml.XmlWriter>
