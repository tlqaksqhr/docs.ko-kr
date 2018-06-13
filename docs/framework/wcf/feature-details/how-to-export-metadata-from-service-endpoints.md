---
title: '방법: 서비스 끝점에서 메타데이터 내보내기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: 9235498956f53d69b3024d1db023f3eb0908d2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491545"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="8ae78-102">방법: 서비스 끝점에서 메타데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="8ae78-102">How to: Export Metadata from Service Endpoints</span></span>
<span data-ttu-id="8ae78-103">이 항목에서는 서비스 끝점으로부터 메타데이터를 내보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="8ae78-104">서비스 끝점에서 메타데이터를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="8ae78-104">To export metadata from service endpoints</span></span>  
  
1.  <span data-ttu-id="8ae78-105">새 Visual Studio Console App Project를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="8ae78-106">다음 단계에 표시된 코드를 생성된 Program.cs 파일의 main() 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2.  <span data-ttu-id="8ae78-107"><xref:System.ServiceModel.Description.WsdlExporter>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3.  <span data-ttu-id="8ae78-108"><xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 속성을 <xref:System.ServiceModel.Description.PolicyVersion> 열거형의 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="8ae78-109">샘플에서는 값을 WS-Policy 1.5에 해당되는 <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4.  <span data-ttu-id="8ae78-110"><xref:System.ServiceModel.Description.ServiceEndpoint> 개체의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5.  <span data-ttu-id="8ae78-111">각 서비스 끝점의 메타데이터를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6.  <span data-ttu-id="8ae78-112">내보내기 프로세스 중에 오류가 발생하지 않았는지 확인하고 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7.  <span data-ttu-id="8ae78-113">이제 <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> 메서드를 호출하여 파일에 쓰는 등의 방식으로 메타데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ae78-114">예제</span><span class="sxs-lookup"><span data-stu-id="8ae78-114">Example</span></span>  
 <span data-ttu-id="8ae78-115">다음은 이 예제에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8ae78-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ae78-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8ae78-116">Compiling the Code</span></span>  
 <span data-ttu-id="8ae78-117">Program.cs를 컴파일할 때에는 System.ServiceModel.dll을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ae78-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae78-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ae78-118">See Also</span></span>  
 [<span data-ttu-id="8ae78-119">메타데이터 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="8ae78-119">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [<span data-ttu-id="8ae78-120">메타데이터 사용</span><span class="sxs-lookup"><span data-stu-id="8ae78-120">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="8ae78-121">끝점: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="8ae78-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
