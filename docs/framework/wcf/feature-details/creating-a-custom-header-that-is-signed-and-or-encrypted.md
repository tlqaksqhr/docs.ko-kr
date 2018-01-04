---
title: "서명 된 사용자 지정 헤더를 작성 하 고-또는 암호화 된"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b0faa62d75c506fd93c17c6a67aaecdd22bc8c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a><span data-ttu-id="6a799-102">서명 된 사용자 지정 헤더를 작성 하 고-또는 암호화 된</span><span class="sxs-lookup"><span data-stu-id="6a799-102">Creating a custom header that is signed and-or encrypted</span></span>
<span data-ttu-id="6a799-103">WCF 클라이언트를 사용하여 WCF 서비스가 아닌 서비스를 호출하는 경우 사용자 지정 SOAP 헤더를 사용해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-103">When calling a non-WCF service using a WCF client it is sometimes necessary to use custom SOAP headers.</span></span> <span data-ttu-id="6a799-104">WCF에는 서명되고 암호화된 사용자 지정 헤더가 WCF 서비스가 아닌 서비스와 작동하지 못하게 하는 정규화 버그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-104">There is a canonicalization bug in WCF that prevents custom headers that are signed and encrypted from working with a non-WCF service.</span></span> <span data-ttu-id="6a799-105">이 문제는 기본 XML 네임스페이스의 잘못된 정규화 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-105">The problem is caused by the incorrect canonicalization of default XML namespaces.</span></span> <span data-ttu-id="6a799-106">이는 서명되거나 암호화된 사용자 지정 헤더를 사용하여 WCF 서비스가 아닌 서비스를 호출하는 경우에만 문제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-106">This is only problematic when calling non-WCF services with custom headers that are signed and/or encrypted.</span></span>  <span data-ttu-id="6a799-107">이러한 서비스에서는 서명되거나 암호화된 사용자 지정 헤더가 포함된 메시지를 받는 경우 서명을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-107">When the service receives the message containing the signed and/or encrypted custom header it is unable to verify the signature.</span></span> <span data-ttu-id="6a799-108">이 해결 방법을 통해 정규화 버그가 방지되고 WCF 서비스가 아닌 서비스와의 상호 운용성이 허용되지만 WCF 서비스와의 상호 운용성이 차단되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-108">This workaround avoids the canonicalization bug, allows interoperability with non-WCF services, but does not prevent interoperability with WCF services.</span></span>  
  
## <a name="defining-the-custom-header"></a><span data-ttu-id="6a799-109">사용자 지정 헤더 정의</span><span class="sxs-lookup"><span data-stu-id="6a799-109">Defining the custom header</span></span>  
 <span data-ttu-id="6a799-110">사용자 지정 헤더는 메시지 계약을 정의하고 <xref:System.ServiceModel.MessageHeaderAttribute> 특성을 사용하여 헤더로 전송할 멤버를 표시하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-110">Custom headers are defined by defining a message contract and marking the members you want to be sent as headers with a <xref:System.ServiceModel.MessageHeaderAttribute> attribute.</span></span> <span data-ttu-id="6a799-111">정규화 버그 문제를 해결하려면 XML serializer가 기본 네임스페이스 선언 대신 접두사와 함께 사용자 지정 헤더의 네임스페이스를 선언하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-111">To work around the canonicalization bug you must ensure that the XML serializer declares the namespace for the custom header with a prefix instead of a default namespace declaration.</span></span> <span data-ttu-id="6a799-112">다음 코드에서는 올바른 네임스페이스 선언과 함께 메시지 헤더로 사용할 데이터 형식을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-112">The following code shows how to define the data type that will be used as a message header with the correct namespace declaration.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="6a799-113">이 코드에서는 XML Serializer를 사용하여 serialize될 `msgHeaderElement`라는 새 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-113">This code declares a new type called `msgHeaderElement` that will be serialized with the XML Serializer.</span></span> <span data-ttu-id="6a799-114">이 형식의 인스턴스가 serialize되면 ‘h’ 접두사를 사용하여 네임스페이스를 정의하므로 정규화 버그가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-114">When an instance of this type is serialized, it will define a namespace with an ‘h’ prefix, thus working around the canonicalization bug.</span></span>  <span data-ttu-id="6a799-115">메시지 계약은 다음 예제와 같이 `msgHeaderElement`의 인스턴스를 정의하고 <xref:System.ServiceModel.MessageHeaderAttribute> 특성을 사용하여 이 인스턴스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a799-115">The message contract would then define an instance of `msgHeaderElement` and mark it with the <xref:System.ServiceModel.MessageHeaderAttribute> attribute as shown in the following example.</span></span>  
  
```  
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a799-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a799-116">See Also</span></span>  
 [<span data-ttu-id="6a799-117">기본 메시지 계약</span><span class="sxs-lookup"><span data-stu-id="6a799-117">Default Message Contract</span></span>](../../../../docs/framework/wcf/samples/default-message-contract.md)  
 [<span data-ttu-id="6a799-118">메시지 계약</span><span class="sxs-lookup"><span data-stu-id="6a799-118">Message Contracts</span></span>](../../../../docs/framework/wcf/samples/message-contracts.md)  
 [<span data-ttu-id="6a799-119">메시지 계약 사용</span><span class="sxs-lookup"><span data-stu-id="6a799-119">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
