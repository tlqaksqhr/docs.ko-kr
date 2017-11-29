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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ac43be1978a2a6e80b08e0c4bcd5e0e92043719e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a>서명 된 사용자 지정 헤더를 작성 하 고-또는 암호화 된
WCF 클라이언트를 사용하여 WCF 서비스가 아닌 서비스를 호출하는 경우 사용자 지정 SOAP 헤더를 사용해야 하는 경우가 있습니다. WCF에는 서명되고 암호화된 사용자 지정 헤더가 WCF 서비스가 아닌 서비스와 작동하지 못하게 하는 정규화 버그가 있습니다. 이 문제는 기본 XML 네임스페이스의 잘못된 정규화 때문에 발생합니다. 이는 서명되거나 암호화된 사용자 지정 헤더를 사용하여 WCF 서비스가 아닌 서비스를 호출하는 경우에만 문제가 됩니다.  이러한 서비스에서는 서명되거나 암호화된 사용자 지정 헤더가 포함된 메시지를 받는 경우 서명을 확인할 수 없습니다. 이 해결 방법을 통해 정규화 버그가 방지되고 WCF 서비스가 아닌 서비스와의 상호 운용성이 허용되지만 WCF 서비스와의 상호 운용성이 차단되지는 않습니다.  
  
## <a name="defining-the-custom-header"></a>사용자 지정 헤더 정의  
 사용자 지정 헤더는 메시지 계약을 정의하고 <xref:System.ServiceModel.MessageHeaderAttribute> 특성을 사용하여 헤더로 전송할 멤버를 표시하여 정의됩니다. 정규화 버그 문제를 해결하려면 XML serializer가 기본 네임스페이스 선언 대신 접두사와 함께 사용자 지정 헤더의 네임스페이스를 선언하도록 해야 합니다. 다음 코드에서는 올바른 네임스페이스 선언과 함께 메시지 헤더로 사용할 데이터 형식을 정의하는 방법을 보여 줍니다.  
  
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
  
 이 코드에서는 XML Serializer를 사용하여 serialize될 `msgHeaderElement`라는 새 형식을 선언합니다. 이 형식의 인스턴스가 serialize되면 ‘h’ 접두사를 사용하여 네임스페이스를 정의하므로 정규화 버그가 해결됩니다.  메시지 계약은 다음 예제와 같이 `msgHeaderElement`의 인스턴스를 정의하고 <xref:System.ServiceModel.MessageHeaderAttribute> 특성을 사용하여 이 인스턴스를 표시합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [기본 메시지 계약](../../../../docs/framework/wcf/samples/default-message-contract.md)  
 [메시지 계약](../../../../docs/framework/wcf/samples/message-contracts.md)  
 [메시지 계약 사용](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
