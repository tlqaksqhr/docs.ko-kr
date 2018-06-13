---
title: '방법: XslTransform 코드 마이그레이션'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fcfe8b0fbbc829c1bee08b761271f4d12b6ae05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571001"
---
# <a name="how-to-migrate-your-xsltransform-code"></a><span data-ttu-id="51ae3-102">방법: XslTransform 코드 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="51ae3-102">How to: Migrate Your XslTransform Code</span></span>
<span data-ttu-id="51ae3-103">새 XSLT 클래스는 기존 클래스와 매우 유사하게 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-103">The new XSLT classes have been designed to be very similar to the existing classes.</span></span> <span data-ttu-id="51ae3-104"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 <xref:System.Xml.Xsl.XslTransform> 클래스를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-104">The <xref:System.Xml.Xsl.XslCompiledTransform> class replaces the <xref:System.Xml.Xsl.XslTransform> class.</span></span> <span data-ttu-id="51ae3-105"><xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 메서드를 사용하여 스타일시트를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-105">Style sheets are compiled using the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span> <span data-ttu-id="51ae3-106"><xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드를 사용하여 변환을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-106">Transforms are executed using the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span> <span data-ttu-id="51ae3-107">다음 프로시저에서는 일반 XSLT 작업을 보여 주고 <xref:System.Xml.Xsl.XslTransform> 클래스를 사용한 코드와 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용한 코드를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-107">The following procedures show common XSLT tasks, and compare the code using the <xref:System.Xml.Xsl.XslTransform> class versus the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a><span data-ttu-id="51ae3-108">파일 및 출력을 URI로 변환하려면</span><span class="sxs-lookup"><span data-stu-id="51ae3-108">To transform a file and output to a URI</span></span>  
  
-   <span data-ttu-id="51ae3-109"><xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-109">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
-   <span data-ttu-id="51ae3-110"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-110">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a><span data-ttu-id="51ae3-111">스타일시트를 컴파일하고 기본 자격 증명으로 확인기를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="51ae3-111">To compile a style sheet and use a resolver with default credentials</span></span>  
  
-   <span data-ttu-id="51ae3-112"><xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-112">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
-   <span data-ttu-id="51ae3-113"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-113">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="51ae3-114">XSLT 매개 변수를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="51ae3-114">To use an XSLT parameter</span></span>  
  
-   <span data-ttu-id="51ae3-115"><xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-115">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
-   <span data-ttu-id="51ae3-116"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-116">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a><span data-ttu-id="51ae3-117">XSLT 스크립트를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="51ae3-117">To enable XSLT scripting</span></span>  
  
-   <span data-ttu-id="51ae3-118"><xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-118">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
-   <span data-ttu-id="51ae3-119"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-119">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a><span data-ttu-id="51ae3-120">결과를 DOM 개체에 로드하려면</span><span class="sxs-lookup"><span data-stu-id="51ae3-120">To load the results into a DOM object</span></span>  
  
-   <span data-ttu-id="51ae3-121"><xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-121">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
-   <span data-ttu-id="51ae3-122"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-122">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51ae3-123"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스에는 XSLT 변환 결과를 <xref:System.Xml.XmlReader> 개체로 반환하는 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-123">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not have a method that returns the XSLT transformation results as an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="51ae3-124">그러나 XML 파일로 출력하고 이 XML 파일을 다른 개체에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-124">However, you can output to an XML file and load the XML file into another object.</span></span>  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a><span data-ttu-id="51ae3-125">결과를 다른 데이터 저장소로 스트리밍하려면</span><span class="sxs-lookup"><span data-stu-id="51ae3-125">To stream the results into another data store</span></span>  
  
-   <span data-ttu-id="51ae3-126"><xref:System.Xml.Xsl.XslTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-126">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
-   <span data-ttu-id="51ae3-127"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="51ae3-127">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="51ae3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51ae3-128">See Also</span></span>  
 [<span data-ttu-id="51ae3-129">XslTransform 클래스에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="51ae3-129">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 [<span data-ttu-id="51ae3-130">XslCompiledTransform 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="51ae3-130">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
