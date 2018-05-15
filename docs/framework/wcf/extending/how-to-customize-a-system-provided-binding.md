---
title: '방법: 시스템 제공 바인딩 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
ms.openlocfilehash: 04b81689d7d625d519a0a9fc8b1fa6df3df16ada
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-customize-a-system-provided-binding"></a><span data-ttu-id="e699b-102">방법: 시스템 제공 바인딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e699b-102">How to: Customize a System-Provided Binding</span></span>
<span data-ttu-id="e699b-103">Windows Communication Foundation (WCF)에 기본 바인딩 요소의 속성 중 일부에 속성을 구성할 수 있도록 여러 시스템 제공 바인딩이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-103">Windows Communication Foundation (WCF) includes several system-provided bindings that allow you to configure some of the properties of the underlying binding elements, but not all of the properties.</span></span> <span data-ttu-id="e699b-104">이 항목에서는 바인딩 요소의 속성을 설정하여 사용자 지정 바인딩을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-104">This topic demonstrates how to set properties on the binding elements to create a custom binding.</span></span>  
  
 <span data-ttu-id="e699b-105">직접 만들고 시스템 제공 바인딩을 사용 하지 않고 바인딩 요소를 구성 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-105">For more information about how to directly create and configure binding elements without using the system-provided bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 <span data-ttu-id="e699b-106">만들기 및 사용자 지정 바인딩 확장에 대 한 자세한 내용은 참조 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-106">For more information about creating and extending custom bindings, see [Extending Bindings](../../../../docs/framework/wcf/extending/extending-bindings.md).</span></span>  
  
 <span data-ttu-id="e699b-107">WCF에서 모든 바인딩에 이루어져 *바인딩 요소의*합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-107">In WCF all bindings are made up of *binding elements*.</span></span> <span data-ttu-id="e699b-108">각 바인딩 요소는 <xref:System.ServiceModel.Channels.BindingElement> 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-108">Each binding element derives from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="e699b-109"><xref:System.ServiceModel.BasicHttpBinding>과 같은 시스템 제공 바인딩은 자체 바인딩 요소를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-109">System-provided bindings such as <xref:System.ServiceModel.BasicHttpBinding> create and configure their own binding elements.</span></span> <span data-ttu-id="e699b-110">이 항목에서는 특히 <xref:System.ServiceModel.BasicHttpBinding> 클래스와 같은 바인딩에서 직접 노출되지 않는 이러한 바인딩 요소의 속성에 액세스하여 이를 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-110">This topic shows you how to access and change the properties of these binding elements, which are not directly exposed on the binding; specifically, the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="e699b-111">개별 바인딩 요소는 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스로 표시되는 컬렉션에 포함되며, 트랜잭션 흐름, 신뢰할 수 있는 세션, 보안, 복합 이중, 단방향, 스트림 보안, 메시지 인코딩 및 전송 순서로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-111">The individual binding elements are contained in a collection represented by the <xref:System.ServiceModel.Channels.BindingElementCollection> class and are added in this order: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, and Transport.</span></span> <span data-ttu-id="e699b-112">나열된 모든 바인딩 요소가 모든 바인딩에서 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-112">Note that not all the binding elements listed are required in every binding.</span></span> <span data-ttu-id="e699b-113">사용자 정의 바인딩 요소도 앞에서 설명한 동일한 순서로 이 바인딩 요소에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-113">User-defined binding elements can also appear in this binding element collection and must appear in the same order as previously described.</span></span> <span data-ttu-id="e699b-114">예를 들어, 사용자 정의 전송은 바인딩 요소 컬렉션의 마지막 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-114">For example, a user-defined transport must be the last element of the binding element collection.</span></span>  
  
 <span data-ttu-id="e699b-115"><xref:System.ServiceModel.BasicHttpBinding> 클래스에는 다음 세 가지 바인딩 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-115">The <xref:System.ServiceModel.BasicHttpBinding> class contains three binding elements:</span></span>  
  
1.  <span data-ttu-id="e699b-116">HTTP 전송(메시지 수준 보안)과 함께 사용되는 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 클래스 또는 전송 계층에서 보안을 제공하는 경우(HTTP 전송 사용) 사용되는 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> 클래스 중 하나인 선택적 보안 바인딩 요소</span><span class="sxs-lookup"><span data-stu-id="e699b-116">An optional security binding element, either the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> class used with the HTTP transport (message level security) or the <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> class, which is used when the transport layer provides security, in which case the HTTPS transport is used.</span></span>  
  
2.  <span data-ttu-id="e699b-117"><xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 또는 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 중 하나인 필수 메시지 인코더 바인딩 요소</span><span class="sxs-lookup"><span data-stu-id="e699b-117">A required message encoder binding element, either <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> or <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span></span>  
  
3.  <span data-ttu-id="e699b-118"><xref:System.ServiceModel.Channels.HttpTransportBindingElement> 또는 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> 중 하나인 필수 전송 바인딩 요소</span><span class="sxs-lookup"><span data-stu-id="e699b-118">A required transport binding element, either <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, or <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
 <span data-ttu-id="e699b-119">다음이 예제에서는 바인딩의 인스턴스를 만들, 생성 한 *사용자 지정 바인딩* 여기에서 사용자 지정 바인딩에서 바인딩 요소를 검사 하 고 설정 HTTP 바인딩 요소를 찾으면 해당 `KeepAliveEnabled` 속성 를`false`.</span><span class="sxs-lookup"><span data-stu-id="e699b-119">In this example we create an instance of the binding, generate a *custom binding* from it, examine the binding elements in the custom binding, and when we find the HTTP binding element, we set its `KeepAliveEnabled` property to `false`.</span></span> <span data-ttu-id="e699b-120">`KeepAliveEnabled` 속성이 `BasicHttpBinding`에서 직접 노출되지 않으므로 사용자 지정 바인딩을 만들어 바인딩 요소 아래에서 탐색하여 이 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-120">The `KeepAliveEnabled` property is not exposed directly on the `BasicHttpBinding`, so we must create a custom binding to navigate down to the binding element and set this property.</span></span>  
  
### <a name="to-modify-a-system-provided-binding"></a><span data-ttu-id="e699b-121">시스템 제공 바인딩을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="e699b-121">To modify a system-provided binding</span></span>  
  
1.  <span data-ttu-id="e699b-122"><xref:System.ServiceModel.BasicHttpBinding> 클래스의 인스턴스를 만들고 보안 모드를 메시지 수준으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-122">Create an instance of the <xref:System.ServiceModel.BasicHttpBinding> class and set its security mode to message-level.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  <span data-ttu-id="e699b-123">바인딩에서 사용자 지정 바인딩을 만들고 사용자 지정 바인딩의 속성 중 하나에서 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-123">Create a custom binding from the binding and create a <xref:System.ServiceModel.Channels.BindingElementCollection> class from one of the custom binding's properties.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <span data-ttu-id="e699b-124"><xref:System.ServiceModel.Channels.BindingElementCollection> 클래스를 순환 검색하여 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 클래스가 있으면 <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e699b-124">Loop through the <xref:System.ServiceModel.Channels.BindingElementCollection> class, and when you find the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> class, set its <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property to `false`.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e699b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e699b-125">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="e699b-126">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="e699b-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
