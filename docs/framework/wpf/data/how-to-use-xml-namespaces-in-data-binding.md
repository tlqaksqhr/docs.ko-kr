---
title: '방법: XML 네임스페이스를 데이터 바인딩에 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 483b59bb7cea25617c832b96690f742b8b64b3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556902"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="79b7f-102">방법: XML 네임스페이스를 데이터 바인딩에 사용</span><span class="sxs-lookup"><span data-stu-id="79b7f-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="79b7f-103">예제</span><span class="sxs-lookup"><span data-stu-id="79b7f-103">Example</span></span>  
 <span data-ttu-id="79b7f-104">이 예제에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 바인딩 소스에 지정된 네임스페이스를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79b7f-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="79b7f-105">[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 다음 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임스페이스 정의가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="79b7f-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="79b7f-106">사용할 수는 <xref:System.Windows.Data.XmlNamespaceMapping> 요소를 네임 스페이스를 한 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>다음 예제와 같이, 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b7f-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="79b7f-107">그런 다음 사용할 수는 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 참조 하는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="79b7f-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="79b7f-108"><xref:System.Windows.Controls.ListBox> 이 예제에 표시 됩니다는 *제목* 및 *dc:date* 각 *항목*합니다.</span><span class="sxs-lookup"><span data-stu-id="79b7f-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="79b7f-109"><xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 사용 하는 것과 일치 하지 않아도 지정는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 원본; 접두사를 변경 하는 경우는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 소스 매핑은 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="79b7f-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="79b7f-110">이 특정 예제는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터는 웹 서비스에서 제공 되지만 <xref:System.Windows.Data.XmlNamespaceMapping> 인라인 요소 에서도 작동 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 포함된 된 파일의 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="79b7f-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b7f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79b7f-111">See Also</span></span>  
 [<span data-ttu-id="79b7f-112">XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩</span><span class="sxs-lookup"><span data-stu-id="79b7f-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="79b7f-113">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="79b7f-113">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="79b7f-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="79b7f-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
