---
title: "Serialization 도구"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b675f-938c-44ff-807b-0ca9fea30103
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33da3336cc78763de080eb21e3b84fd4cfdc7716
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="serialization-tools"></a><span data-ttu-id="b81e0-102">Serialization 도구</span><span class="sxs-lookup"><span data-stu-id="b81e0-102">Serialization Tools</span></span>
<span data-ttu-id="b81e0-103">이 단원에는 serialization 도구에 대한 자세한 설명이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-103">This section contains detailed information about the serialization tools.</span></span> <span data-ttu-id="b81e0-104">명령줄에서 모든 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-104">You can run all the tools from the command line.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b81e0-105">.NET Framework 도구에서 제대로 작동되도록 하려면 Path, Include 및 Lib 환경 변수를 올바르게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-105">For the .NET Framework tools to function properly, you must set your Path, Include, and Lib environment variables correctly.</span></span> <span data-ttu-id="b81e0-106">\<SDK>\v2.0\Bin 디렉터리에 저장된 SDKVars.bat를 실행하여 이러한 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-106">Set these environment variables by running SDKVars.bat, which is located in the \<SDK>\v2.0\Bin directory.</span></span> <span data-ttu-id="b81e0-107">SDKVars.bat를 모든 명령 셸에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-107">SDKVars.bat must be executed in every command shell.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b81e0-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b81e0-108">In This Section</span></span>  
  
|<span data-ttu-id="b81e0-109">도구</span><span class="sxs-lookup"><span data-stu-id="b81e0-109">Tool</span></span>|<span data-ttu-id="b81e0-110">설명</span><span class="sxs-lookup"><span data-stu-id="b81e0-110">Description</span></span>|  
|----------|-----------------|  
|[<span data-ttu-id="b81e0-111">XML 직렬 변환기 생성기 도구(Sgen.exe)</span><span class="sxs-lookup"><span data-stu-id="b81e0-111">XML Serializer Generator Tool (Sgen.exe)</span></span>](../../../docs/standard/serialization/xml-serializer-generator-tool-sgen-exe.md)|<span data-ttu-id="b81e0-112"><xref:System.Xml.Serialization.XmlSerializer>의 런타임 성능을 향상시키기 위해 지정된 어셈블리의 형식에 대해 XML serialization 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-112">Creates an XML serialization assembly for types in a specified assembly in order to improve the run-time performance of the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="b81e0-113">XML 스키마 정의 도구(Xsd.exe)</span><span class="sxs-lookup"><span data-stu-id="b81e0-113">XML Schema Definition Tool (Xsd.exe)</span></span>](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)|<span data-ttu-id="b81e0-114">W3C(World Wide Web 컨소시엄)에서 제시한 XSD 언어를 따르는 XML 스키마를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-114">Generates XML schemas that follow the XSD language proposed by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="b81e0-115">이 도구는 공용 언어 런타임 클래스 및 XSD 스키마 파일의 <xref:System.Data.DataSet> 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b81e0-115">This tool generates common language runtime classes and <xref:System.Data.DataSet> classes from an XSD schema file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b81e0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b81e0-116">See Also</span></span>  
 [<span data-ttu-id="b81e0-117">도구</span><span class="sxs-lookup"><span data-stu-id="b81e0-117">Tools</span></span>](../../../docs/framework/tools/index.md)
