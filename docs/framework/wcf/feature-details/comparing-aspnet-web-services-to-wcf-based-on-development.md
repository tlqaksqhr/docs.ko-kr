---
title: "개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 82fb1848fc329db2921b626a894b9f91e766cd30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="d9544-102">개발을 기반으로 ASP.NET 웹 서비스와 WCF 비교</span><span class="sxs-lookup"><span data-stu-id="d9544-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d9544-103">에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 ASP.NET 웹 서비스처럼 프로그래밍하고 구성하며 동작을 모방하도록 할 수 있는 ASP.NET 호환 모드 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-103"> has an ASP.NET compatibility mode option to enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="d9544-104">다음 단원에서는 ASP.NET 웹 서비스와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 응용 프로그램을 개발하는 데 필요한 사항을 기반으로 이 두 가지 기술을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-104">The following sections compare ASP.NET Web services and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] based on what is required to develop applications using both technologies.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="d9544-105">데이터 표현</span><span class="sxs-lookup"><span data-stu-id="d9544-105">Data Representation</span></span>  
 <span data-ttu-id="d9544-106">ASP.NET을 사용하여 웹 서비스를 개발하는 경우 일반적으로 서비스에서 사용할 복합 데이터 형식을 정의하는 것부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="d9544-107">ASP.NET에서는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 .NET Framework 형식으로 표현된 데이터를 서비스와의 전송을 위한 XML로 변환하고 XML로 받은 데이터를 .NET Framework 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="d9544-108">ASP.NET 서비스에서 사용할 복합 데이터 형식을 정의하려면 <xref:System.Xml.Serialization.XmlSerializer>가 XML로 또는 XML에서 serialize할 수 있는 .NET Framework 클래스를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="d9544-109">이러한 클래스는 수동으로 작성하거나, 명령줄 XML 스키마/데이터 형식 지원 유틸리티인 xsd.exe를 사용하여 XML 스키마의 형식 정의에서 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>  
  
 <span data-ttu-id="d9544-110">아래 목록에서는 <xref:System.Xml.Serialization.XmlSerializer>가 XML로 또는 XML에서 serialize할 수 있는 .NET Framework 클래스를 정의할 때 알아야 할 주요 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>  
  
-   <span data-ttu-id="d9544-111">.NET Framework 개체의 public 필드와 속성만 XML로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>  
  
-   <span data-ttu-id="d9544-112">클래스가 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.ICollection> 인터페이스를 구현하는 경우에만 컬렉션 클래스의 인스턴스를 XML로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>  
  
-   <span data-ttu-id="d9544-113"><xref:System.Collections.IDictionary>과 같은 <xref:System.Collections.Hashtable> 인터페이스를 구현하는 클래스는 XML로 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>  
  
-   <span data-ttu-id="d9544-114">클래스의 인스턴스가 XML로 표현되는 방식을 제어하기 위해 <xref:System.Xml.Serialization> 네임스페이스의 여러 가지 특성 형식을 .NET Framework 클래스와 클래스의 멤버에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d9544-115"> 응용 프로그램 개발 역시 일반적으로 복합 형식을 정의하는 것부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-115"> application development usually also begins with the definition of complex types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d9544-116">를 ASP.NET 웹 서비스와 동일한 .NET Framework 형식을 사용하도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-116"> can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="d9544-117">다음 샘플 코드에서와 같이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>를 .NET Framework 형식에 추가하여 해당 형식의 인스턴스가 XML로 serialize되도록 지정하고 이 형식에서 serialize되는 특정 필드 또는 속성을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>  
  
```  
//Example One:   
[DataContract]  
public class LineItem  
{  
    [DataMember]  
    public string ItemNumber;  
    [DataMember]  
    public decimal Quantity;  
    [DataMember]  
    public decimal UnitPrice;  
}  
  
//Example Two:   
public class LineItem  
{  
    [DataMember]  
    private string itemNumber;  
    [DataMember]  
    private decimal quantity;  
    [DataMember]  
    private decimal unitPrice;  
  
    public string ItemNumber  
    {  
      get  
      {  
          return this.itemNumber;  
      }  
  
      set  
      {  
          this.itemNumber = value;  
      }  
    }  
  
    public decimal Quantity  
    {  
        get  
        {  
            return this.quantity;  
        }  
  
        set  
        {  
            this.quantity = value;  
        }  
    }  
  
    public decimal UnitPrice  
    {  
      get  
      {  
          return this.unitPrice;  
      }  
  
      set  
      {  
          this.unitPrice = value;  
      }  
    }  
}  
  
//Example Three:   
public class LineItem  
{  
     private string itemNumber;  
     private decimal quantity;  
     private decimal unitPrice;  
  
     [DataMember]  
     public string ItemNumber  
     {  
       get  
       {  
          return this.itemNumber;  
       }  
  
       set  
       {  
           this.itemNumber = value;  
       }  
     }  
  
     [DataMember]  
     public decimal Quantity  
     {  
          get  
          {  
              return this.quantity;  
          }  
  
          set  
          {  
             this.quantity = value;  
          }  
     }  
  
     [DataMember]  
     public decimal UnitPrice  
     {  
          get  
          {  
              return this.unitPrice;  
          }  
  
          set  
          {  
              this.unitPrice = value;  
          }  
     }  
}  
```  
  
 <span data-ttu-id="d9544-118"><xref:System.Runtime.Serialization.DataContractAttribute>는 형식의 필드 또는 속성을 0개 이상 serialize하도록 지정하고, <xref:System.Runtime.Serialization.DataMemberAttribute>는 특정 필드 또는 속성을 serialize하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="d9544-119"><xref:System.Runtime.Serialization.DataContractAttribute>는 클래스 또는 구조체에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="d9544-120"><xref:System.Runtime.Serialization.DataMemberAttribute>는 필드 또는 속성에 적용될 수 있으며, 이 특성이 적용되는 필드와 속성은 public 또는 private일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="d9544-121"><xref:System.Runtime.Serialization.DataContractAttribute>가 적용된 형식의 인스턴스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 데이터 계약이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="d9544-122">이러한 인스턴스는 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 XML로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="d9544-123">아래 목록에서는 <xref:System.Runtime.Serialization.DataContractSerializer>와 <xref:System.Xml.Serialization.XmlSerializer>를 사용할 때의 중요한 차이점과 <xref:System.Xml.Serialization> 네임스페이스의 다양한 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>  
  
-   <span data-ttu-id="d9544-124"><xref:System.Xml.Serialization.XmlSerializer> 및 <xref:System.Xml.Serialization> 네임스페이스의 특성은 .NET Framework 형식을 XML 스키마에 정의된 유효한 형식에 매핑할 수 있도록 고안되었으므로 .NET Framework 형식을 XML로 표현하는 방식을 매우 자세하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="d9544-125"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute>는 형식을 XML로 표현하는 방식을 거의 제어하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="d9544-126">형식과 해당 필드 또는 속성을 XML로 표현하는 데 사용되는 네임스페이스와 이름, 그리고 필드와 속성이 XML로 나타나는 순서만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>  
  
    ```  
    [DataContract(  
    Namespace="urn:Contoso:2006:January:29",  
    Name="LineItem")]  
    public class LineItem  
    {  
         [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]  
         public string itemNumber;  
         [DataMember(Name="Quantity",IsRequired=false,Order = 1)]  
         public decimal quantity;  
         [DataMember(Name="Price",IsRequired=false,Order = 2)]  
         public decimal unitPrice;  
    }  
    ```  
  
     <span data-ttu-id="d9544-127">.NET 형식을 표현하는 데 사용되는 XML의 구조에 관한 다른 모든 요소는 <xref:System.Runtime.Serialization.DataContractSerializer>에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
-   <span data-ttu-id="d9544-128">형식을 XML로 표현하는 방식에 대해 많은 제어를 허용하지 않기 때문에 <xref:System.Runtime.Serialization.DataContractSerializer>에 대해 serialization 프로세스의 예측이 매우 쉽고, 따라서 최적화가 더 용이합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="d9544-129"><xref:System.Runtime.Serialization.DataContractSerializer> 디자인의 실질적 이점은 약 10% 정도의 성능 향상에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>  
  
-   <span data-ttu-id="d9544-130"><xref:System.Xml.Serialization.XmlSerializer>에서 사용하는 특성은 XML로 serialize될 형식의 필드 또는 속성을 표시하지 않지만, <xref:System.Runtime.Serialization.DataMemberAttribute>에서 사용하는 <xref:System.Runtime.Serialization.DataContractSerializer>는 serialize될 필드 또는 속성을 명시적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="d9544-131">따라서 데이터 계약은 응용 프로그램에서 보내고 받을 데이터의 구조에 대한 명시적 계약이라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>  
  
-   <span data-ttu-id="d9544-132"><xref:System.Xml.Serialization.XmlSerializer>는 .NET 개체의 public 멤버만 XML로 변환할 수 있지만 <xref:System.Runtime.Serialization.DataContractSerializer>는 개체 멤버의 액세스 한정자에 관계없이 이러한 멤버를 XML로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>  
  
-   <span data-ttu-id="d9544-133">형식의 public이 아닌 멤버를 XML로 serialize할 수 있기 때문에 <xref:System.Runtime.Serialization.DataContractSerializer>에는 XML로 serialize할 수 있는 .NET 형식의 다양성에 대한 제한이 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="d9544-134">특히 <xref:System.Collections.Hashtable> 인터페이스를 구현하는 <xref:System.Collections.IDictionary>과 같은 XML 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="d9544-135">일반적으로 <xref:System.Runtime.Serialization.DataContractSerializer>는 형식의 정의를 수정하거나 형식을 위한 래퍼를 개발하지 않고도 기존 .NET 형식의 인스턴스를 XML로 serialize할 수 있는 가능성이 훨씬 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>  
  
-   <span data-ttu-id="d9544-136"><xref:System.Runtime.Serialization.DataContractSerializer>가 형식의 public이 아닌 멤버에 액세스할 수 있다는 점에 기인한 또 다른 결과는 <xref:System.Xml.Serialization.XmlSerializer>와 달리 완전 신뢰가 필요하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="d9544-137">완전 신뢰 코드 액세스 권한이 있으면 코드를 실행하는 자격 증명을 사용하여 액세스할 수 있는 컴퓨터의 모든 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-137">The Full Trust code access permission give complete access to all resources on a machine that can be access using the credentials under which the code is executing.</span></span> <span data-ttu-id="d9544-138">완전 신뢰 코드는 컴퓨터의 모든 리소스에 대한 액세스 권한을 부여하므로 이 옵션을 사용할 때는 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-138">This options should be used with care as fully trusted code accesses all resources on your machine.</span></span>  
  
-   <span data-ttu-id="d9544-139"><xref:System.Runtime.Serialization.DataContractSerializer>는 버전 관리를 위한 일부 지원을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>  
  
    -   <span data-ttu-id="d9544-140"><xref:System.Runtime.Serialization.DataMemberAttribute>에는 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> 속성이 있습니다. 이 속성에는 새 버전의 데이터 계약에 추가된, 이전 버전에는 없었던 멤버에 대해 false 값을 할당할 수 있기 때문에 새 버전의 계약이 있는 응용 프로그램에서 이전 버전을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>  
  
    -   <span data-ttu-id="d9544-141">데이터 계약에서 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현하도록 함으로써 <xref:System.Runtime.Serialization.DataContractSerializer>가 새 버전의 데이터 계약에 정의된 멤버를 이전 버전의 계약을 사용하는 응용 프로그램을 통해 전달하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>  
  
 <span data-ttu-id="d9544-142">이러한 모든 차이점에도 불구하고 <xref:System.Xml.Serialization.XmlSerializer>에서 기본적으로 형식을 serialize하는 XML은 해당 XML에 대한 네임스페이스가 명시적으로 정의되어 있는 경우 <xref:System.Runtime.Serialization.DataContractSerializer>에서 형식을 serialize하는 XML과 의미상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="d9544-143">따라서 다음과 같이 두 serializer에서 사용하는 특성을 가지고 있는 클래스는 <xref:System.Xml.Serialization.XmlSerializer>와 <xref:System.Runtime.Serialization.DataContractAttribute>에서 의미상 동일한 XML로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-143">The following class, which has attributes for use with both of the serializers, are translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>  
  
```  
[Serializable]  
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]  
[DataContract(Namespace="urn:Contoso:2006:January:29")]  
public class LineItem  
{  
     [DataMember]  
     public string ItemNumber;  
     [DataMember]  
     public decimal Quantity;  
     [DataMember]  
     public decimal UnitPrice;  
}  
```  
  
 <span data-ttu-id="d9544-144">Windows 소프트웨어 개발 키트 (SDK) 명령줄 도구가 포함 된 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다. ASP.NET 웹 서비스와 함께 사용 되는 xsd.exe 도구와 같은 Svcutil.exe XML 스키마에서.NET 데이터 형식의 정의 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="d9544-145"><xref:System.Runtime.Serialization.DataContractSerializer>에서 XML 스키마에 의해 정의된 형식의 XML을 내보낼 수 있으면 이러한 형식은 데이터 계약이 됩니다. 그렇지 않으면 이러한 형식은 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-145">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d9544-146">Svcutil.exe 도구는 또한 `/dataContractOnly` 스위치를 사용하여 데이터 계약에서 XML 스키마를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-146">The tool, Svcutil.exe, can also be made to generate XML Schema from data contracts using its `/dataContractOnly` switch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9544-147">ASP.NET 웹 서비스에서 <xref:System.Xml.Serialization.XmlSerializer>를 사용하고, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET 호환 모드를 통해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 ASP.NET 웹 서비스의 동작을 모방하는 경우에도 ASP.NET 호환 옵션에서 <xref:System.Xml.Serialization.XmlSerializer>를 사용하도록 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-147">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode makes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="d9544-148">ASP.NET 호환 모드에서 실행되는 서비스에서 <xref:System.Runtime.Serialization.DataContractSerializer>를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-148">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="d9544-149">서비스 개발</span><span class="sxs-lookup"><span data-stu-id="d9544-149">Service Development</span></span>  
 <span data-ttu-id="d9544-150">ASP.NET을 사용하여 서비스를 개발하려면 일반적으로 클래스에 <xref:System.Web.Services.WebService> 특성을 추가하고 서비스의 작업이 되는 해당 클래스의 메서드에 <xref:System.Web.Services.WebMethodAttribute>를 추가했었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-150">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>  
  
```  
[WebService]  
public class Service : T:System.Web.Services.WebService  
{  
    [WebMethod]  
    public string Echo(string input)   
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="d9544-151">ASP.NET 2.0에는 클래스가 아니라 인터페이스에 <xref:System.Web.Services.WebService> 및 <xref:System.Web.Services.WebMethodAttribute> 특성을 추가하고 해당 인터페이스를 구현하기 위해 클래스를 작성하는 옵션이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-151">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <span data-ttu-id="d9544-152">같은 계약을 여러 가지 방식으로 구현하는 다양한 클래스에 사용할 수 있는 서비스의 수행 작업에 대한 계약은 <xref:System.Web.Services.WebService> 특성을 가진 인터페이스로 구성되므로 이 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-152">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="d9544-153">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 하나 이상의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점을 정의함으로써 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-153">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is provided by defining one or more [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints.</span></span> <span data-ttu-id="d9544-154">끝점은 주소, 바인딩 및 서비스 계약으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-154">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="d9544-155">주소는 서비스가 있는 위치를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-155">The address defines where the service is located.</span></span> <span data-ttu-id="d9544-156">바인딩은 서비스와 통신하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-156">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="d9544-157">서비스 계약은 서비스에서 수행할 수 있는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-157">The service contract defines the operations that the service can perform.</span></span>  
  
 <span data-ttu-id="d9544-158">일반적으로 서비스 계약은 다음과 같이 인터페이스에 <xref:System.ServiceModel.ServiceContractAttribute> 및 <xref:System.ServiceModel.OperationContractAttribute>를 추가함으로써 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-158">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>  
  
```  
[ServiceContract]  
public interface IEcho  
{  
     [OperationContract]  
     string Echo(string input);  
}  
```  
  
 <span data-ttu-id="d9544-159"><xref:System.ServiceModel.ServiceContractAttribute>는 인터페이스에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 계약을 정의하도록 지정하고, <xref:System.ServiceModel.OperationContractAttribute>는 서비스 계약의 작업을 정의하는 인터페이스의 메서드(있는 경우)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-159">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>  
  
 <span data-ttu-id="d9544-160">서비스 계약은 일단 정의되면 다음과 같이 클래스로 하여금 서비스 계약을 정의하는 인터페이스를 구현하도록 함으로써 클래스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-160">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>  
  
```  
public class Service : IEcho  
{  
    public string Echo(string input)  
    {  
       return input;  
    }  
}  
```  
  
 <span data-ttu-id="d9544-161">서비스 계약을 구현하는 클래스를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서비스 유형이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-161">A class that implements a service contract is referred to as a service type in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="d9544-162">다음 단계는 주소 및 바인딩을 서비스 유형과 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-162">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="d9544-163">이 작업은 일반적으로 구성 파일을 직접 편집하거나 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공되는 구성 편집기를 사용하여 구성 파일에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-163">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="d9544-164">다음은 구성 파일의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-164">Here is an example of a configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
     <system.serviceModel>  
      <services>  
      <service name="Service ">  
       <endpoint   
        address="EchoService"  
        binding="basicHttpBinding"  
        contract="IEchoService "/>  
      </service>  
      </services>  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="d9544-165">바인딩은 응용 프로그램과의 통신을 위한 프로토콜 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-165">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="d9544-166">다음 표에서는 일반 옵션을 나타내는 시스템 제공 바인딩을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-166">The following table lists the system-provided bindings that represent common options.</span></span>  
  
|<span data-ttu-id="d9544-167">이름</span><span class="sxs-lookup"><span data-stu-id="d9544-167">Name</span></span>|<span data-ttu-id="d9544-168">용도</span><span class="sxs-lookup"><span data-stu-id="d9544-168">Purpose</span></span>|  
|----------|-------------|  
|<span data-ttu-id="d9544-169">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-169">BasicHttpBinding</span></span>|<span data-ttu-id="d9544-170">WS-BasicProfile 1.1 및 Basic Security Profile 1.0을 지원하는 웹 서비스 및 클라이언트와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d9544-170">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|  
|<span data-ttu-id="d9544-171">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-171">WSHttpBinding</span></span>|<span data-ttu-id="d9544-172">HTTP를 통한 WS-* 프로토콜을 지원하는 웹 서비스 및 클라이언트와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d9544-172">Interoperability with Web services and clients that support the WS-* protocols over HTTP.</span></span>|  
|<span data-ttu-id="d9544-173">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-173">WSDualHttpBinding</span></span>|<span data-ttu-id="d9544-174">이중 HTTP 통신(초기 메시지 수신자가 초기 송신자에게 직접 응답하지 않고, 일정 기간에 걸쳐 WS-* 프로토콜을 따르는 HTTP를 사용하여 원하는 수의 응답을 전송할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d9544-174">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-* protocols.</span></span>|  
|<span data-ttu-id="d9544-175">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-175">WSFederationBinding</span></span>|<span data-ttu-id="d9544-176">HTTP 통신(명시적으로 식별된 자격 증명 공급자가 발행한 자격 증명에 따라 서비스의 리소스에 대한 액세스를 제어할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d9544-176">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|  
|<span data-ttu-id="d9544-177">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-177">NetTcpBinding</span></span>|<span data-ttu-id="d9544-178">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소프트웨어 엔터티 간의 네트워크를 통한 안정적인 고성능 보안 통신</span><span class="sxs-lookup"><span data-stu-id="d9544-178">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities across a network.</span></span>|  
|<span data-ttu-id="d9544-179">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-179">NetNamedPipeBinding</span></span>|<span data-ttu-id="d9544-180">같은 컴퓨터에 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소프트웨어 엔터티 간의 안정적인 고성능 보안 통신</span><span class="sxs-lookup"><span data-stu-id="d9544-180">Secure, reliable, high-performance communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities on the same machine.</span></span>|  
|<span data-ttu-id="d9544-181">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-181">NetMsmqBinding</span></span>|<span data-ttu-id="d9544-182">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소프트웨어 엔터티 간의 MSMQ를 사용한 통신</span><span class="sxs-lookup"><span data-stu-id="d9544-182">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using MSMQ.</span></span>|  
|<span data-ttu-id="d9544-183">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-183">MsmqIntegrationBinding</span></span>|<span data-ttu-id="d9544-184">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소프트웨어 엔터티와 다른 소프트웨어 엔터티 간의 MSMQ를 사용한 통신</span><span class="sxs-lookup"><span data-stu-id="d9544-184">Communication between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entity and another software entity by using MSMQ.</span></span>|  
|<span data-ttu-id="d9544-185">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="d9544-185">NetPeerTcpBinding</span></span>|<span data-ttu-id="d9544-186">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 소프트웨어 엔터티 간의 Windows 피어 투 피어 네트워킹을 사용한 통신</span><span class="sxs-lookup"><span data-stu-id="d9544-186">Communication between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] software entities by using Windows Peer-to-Peer Networking.</span></span>|  
  
 <span data-ttu-id="d9544-187">시스템 제공 바인딩인 <xref:System.ServiceModel.BasicHttpBinding>은 ASP.NET 웹 서비스에서 지원되는 프로토콜 집합을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-187">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>  
  
 <span data-ttu-id="d9544-188">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램용 사용자 지정 바인딩은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 개별 프로토콜을 구현하는 데 사용하는 바인딩 요소 클래스의 컬렉션으로 쉽게 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-188">Custom bindings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are easily defined as collections of the binding element classes that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses to implement individual protocols.</span></span> <span data-ttu-id="d9544-189">새 바인딩 요소를 작성하여 추가 프로토콜을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-189">New binding elements can be written to represent additional protocols.</span></span>  
  
 <span data-ttu-id="d9544-190">서비스 유형의 내부 동작은 동작이라는 클래스 모음의 속성을 사용하여 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-190">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="d9544-191">다음 예제에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute> 클래스를 사용하여 서비스 유형이 다중 스레드되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-191">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple]  
public class DerivativesCalculatorServiceType: IDerivativesCalculator  
```  
  
 <span data-ttu-id="d9544-192"><xref:System.ServiceModel.ServiceBehaviorAttribute>와 같은 일부 동작은 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-192">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="d9544-193">관리자가 설정할 수 있는 속성이 있는 다른 동작은 응용 프로그램의 구성에서 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-193">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>  
  
 <span data-ttu-id="d9544-194">서비스 유형 프로그래밍에서는 <xref:System.ServiceModel.OperationContext> 클래스가 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-194">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="d9544-195">이 클래스의 정적 <xref:System.ServiceModel.OperationContext.Current%2A> 속성은 작업이 실행되고 있는 컨텍스트의 정보에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-195">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="d9544-196">따라서 <xref:System.ServiceModel.OperationContext>는 <xref:System.Web.HttpContext> 및 <xref:System.EnterpriseServices.ContextUtil> 클래스와 모두 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-196"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="d9544-197">호스팅</span><span class="sxs-lookup"><span data-stu-id="d9544-197">Hosting</span></span>  
 <span data-ttu-id="d9544-198">ASP.NET 웹 서비스는 클래스 라이브러리 어셈블리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-198">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="d9544-199">확장명이 .asmx인 서비스 파일이라는 파일이 제공됩니다. 이 파일에는 서비스에 대한 코드를 포함하는 클래스와 이 클래스가 있는 어셈블리를 식별하는 `@ WebService` 지시문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-199">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>  
  
```  
<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>  
```  
  
 <span data-ttu-id="d9544-200">서비스 파일은 IIS(인터넷 정보 서비스)의 ASP.NET 응용 프로그램 루트에 복사되고, 어셈블리는 이 응용 프로그램 루트의 \bin 하위 디렉터리에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-200">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="d9544-201">그런 다음 응용 프로그램 루트에 있는 서비스 파일의 URL(Uniform Resource Locator)을 사용하여 이 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-201">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d9544-202"> 서비스는 IIS 5.1 또는 6.0, IIS 7.0의 일부로 제공되는 WAS(Windows Process Activation Service), 그리고 모든 .NET 응용 프로그램 내에서 즉시 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-202"> services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="d9544-203">IIS 5.1 또는 6.0에서 서비스를 호스트하려면 이 서비스가 HTTP를 통신 전송 프로토콜로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-203">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>  
  
 <span data-ttu-id="d9544-204">IIS 5.1, 6.0 또는 WAS에서 서비스를 호스트하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-204">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>  
  
1.  <span data-ttu-id="d9544-205">서비스 유형을 클래스 라이브러리 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-205">Compile the service type into a class library assembly.</span></span>  
  
2.  <span data-ttu-id="d9544-206">다음과 같은 서비스 유형을 식별하는 `@ ServiceHost` 지시문이 포함된 서비스 파일(확장명 .svc)로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-206">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>  
  
    ```  
    <%@ServiceHost language="c#" Service="MyService" %>  
    ```  
  
3.  <span data-ttu-id="d9544-207">서비스 파일을 가상 디렉터리에 복사하고 어셈블리를 이 가상 디렉터리의 \bin 하위 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-207">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>  
  
4.  <span data-ttu-id="d9544-208">구성 파일을 가상 디렉터리에 복사하고 파일 이름을 Web.config로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-208">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>  
  
 <span data-ttu-id="d9544-209">그러면 응용 프로그램 루트에 있는 서비스 파일의 URL을 사용하여 해당 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-209">The application is then accessible by using the URL of the service file in the application root.</span></span>  
  
 <span data-ttu-id="d9544-210">.NET 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스트하려면 서비스 유형을 이 응용 프로그램에서 참조하는 클래스 라이브러리 어셈블리로 컴파일하고, <xref:System.ServiceModel.ServiceHost> 클래스를 사용하여 해당 서비스를 호스트하도록 응용 프로그램을 프로그래밍합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-210">To host a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="d9544-211">다음은 필요한 기본 프로그래밍 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-211">The following is an example of the basic programming required:</span></span>  
  
```  
string httpBaseAddress = "http://www.contoso.com:8000/";  
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";  
  
Uri httpBaseAddressUri = new Uri(httpBaseAddress);  
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);  
  
Uri[] baseAdresses = new Uri[] {   
 httpBaseAddressUri,  
 tcpBaseAddressUri};  
  
using(ServiceHost host = new ServiceHost(  
typeof(Service), //"Service" is the name of the service type baseAdresses))  
{  
     host.Open();  
  
     […] //Wait to receive messages  
     host.Close();  
}  
```  
  
 <span data-ttu-id="d9544-212">이 예제에서는 <xref:System.ServiceModel.ServiceHost> 생성에서 하나 이상의 전송 프로토콜에 대한 주소가 지정되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-212">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d9544-213">이러한 주소를 기본 주소라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-213">These addresses are referred to as base addresses.</span></span>  
  
 <span data-ttu-id="d9544-214">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 끝점에 제공되는 주소는 끝점의 호스트에 대한 기본 주소에 상대적인 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-214">The address provided for any endpoint of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="d9544-215">호스트에는 통신 전송 프로토콜마다 기본 주소가 하나씩 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-215">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="d9544-216">이전 구성 파일의 샘플 구성에서 끝점에 대해 선택된 <xref:System.ServiceModel.BasicHttpBinding>은 HTTP를 전송 프로토콜로 사용하므로 `EchoService` 끝점의 주소는 호스트의 HTTP 기본 주소에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-216">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="d9544-217">이전 예제에서 호스트의 경우 HTTP 기본 주소는 http://www.contoso.com:8000/입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-217">In the case of the host in the preceding example, the HTTP base address is http://www.contoso.com:8000/.</span></span> <span data-ttu-id="d9544-218">IIS 또는 WAS에서 호스트되는 서비스의 기본 주소는 해당 서비스에 대한 서비스 파일의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-218">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>  
  
 <span data-ttu-id="d9544-219">IIS 또는 WAS에서 호스트되고 전송 프로토콜로 HTTP만 사용하도록 구성된 서비스만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET 호환 모드 옵션을 사용하도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-219">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode option.</span></span> <span data-ttu-id="d9544-220">이 옵션을 사용하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-220">Turning that option on requires the following steps.</span></span>  
  
1.  <span data-ttu-id="d9544-221">프로그래머는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> 특성을 서비스 유형에 추가하여 ASP.NET 호환 모드가 허용되는지 또는 필수인지 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-221">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>  
  
    ```  
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(  
          RequirementsMode=AspNetCompatbilityRequirementsMode.Require)]  
    public class DerivativesCalculatorServiceType: IDerivativesCalculator  
    ```  
  
2.  <span data-ttu-id="d9544-222">관리자는 ASP.NET 호환 모드를 사용하도록 응용 프로그램을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-222">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>  
  
    ```xml  
    <configuration>  
         <system.serviceModel>  
          <services>  
          […]  
          </services>  
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="d9544-223">서비스 파일의 확장명으로 .svc가 아닌 .asmx를 사용하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>  
  
    ```xml  
    <system.web>  
         <compilation>  
          <compilation debug="true">  
          <buildProviders>  
           <remove extension=".asmx"/>  
           <add extension=".asmx"   
            type="System.ServiceModel.ServiceBuildProvider,   
            Systemm.ServiceModel,   
            Version=3.0.0.0,   
            Culture=neutral,   
            PublicKeyToken=b77a5c561934e089" />  
          </buildProviders>  
          </compilation>  
         </compilation>  
    </system.web>  
    ```  
  
     <span data-ttu-id="d9544-224">이 옵션을 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하도록 서비스를 수정할 때 .asmx 서비스 파일의 URL을 사용하도록 구성된 클라이언트를 수정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-224">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="client-development"></a><span data-ttu-id="d9544-225">클라이언트 개발</span><span class="sxs-lookup"><span data-stu-id="d9544-225">Client Development</span></span>  
 <span data-ttu-id="d9544-226">ASP.NET 웹 서비스용 클라이언트는 .asmx 파일의 URL을 입력으로 제공하는 WSDL.exe 명령줄 도구를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-226">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="d9544-227">제공 하는 해당 도구 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 은 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-227">The corresponding tool provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="d9544-228">이 도구는 서비스 계약과 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스에 대한 정의를 포함한 코드 모듈을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-228">It generates a code module with the definition of the service contract and the definition of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class.</span></span> <span data-ttu-id="d9544-229">또한 서비스의 주소와 바인딩을 포함한 구성 파일도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-229">It also generates a configuration file with the address and binding of the service.</span></span>  
  
 <span data-ttu-id="d9544-230">원격 서비스의 클라이언트를 프로그래밍할 때 일반적으로 비동기 패턴에 따라 프로그래밍하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-230">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="d9544-231">WSDL.exe 도구로 생성되는 코드는 기본적으로 항상 동기 패턴과 비동기 패턴을 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-231">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="d9544-232">생성 된 코드는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 패턴 중 하나에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-232">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="d9544-233">이 도구는 기본적으로 동기 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-233">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="d9544-234">이 도구를 `/async` 스위치와 함께 실행하면 생성된 코드에서 비동기 패턴을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-234">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>  
  
 <span data-ttu-id="d9544-235">ASP.NET의 WSDL.exe 도구로 생성되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스에 있는 이름과 Svcutil.exe 도구로 생성되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 클래스에 있는 이름이 일치하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-235">There is no guarantee that names in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="d9544-236">특히 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize되어야 하는 클래스의 속성 이름에는 Svcutil.exe 도구로 생성되는 코드의 경우 기본적으로 Property 접미사가 지정되지만 WSDL.exe 도구로 생성되는 코드의 경우에는 Property 접미사가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-236">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>  
  
## <a name="message-representation"></a><span data-ttu-id="d9544-237">메시지 표현</span><span class="sxs-lookup"><span data-stu-id="d9544-237">Message Representation</span></span>  
 <span data-ttu-id="d9544-238">ASP.NET 웹 서비스에서 보내고 받는 SOAP 메시지의 헤더를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-238">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="d9544-239"><xref:System.Web.Services.Protocols.SoapHeader>에서 클래스가 파생되어 헤더의 구조가 정의된 다음 <xref:System.Web.Services.Protocols.SoapHeaderAttribute>가 헤더의 존재를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-239">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>  
  
```  
public class SomeProtocol : SoapHeader  
{  
     public long CurrentValue;  
     public long Total;  
}  
  
[WebService]  
public interface IEcho  
{  
     SomeProtocol ProtocolHeader  
     {  
      get;  
     set;  
     }  
  
     [WebMethod]  
     [SoapHeader("ProtocolHeader")]  
     string PlaceOrders(PurchaseOrderType order);  
}  
  
public class Service: WebService, IEcho  
{  
     private SomeProtocol protocolHeader;  
  
     public SomeProtocol ProtocolHeader  
     {  
         get  
         {  
              return this.protocolHeader;  
         }  
  
         set  
         {  
              this.protocolHeader = value;  
         }  
     }  
  
     string PlaceOrders(PurchaseOrderType order)  
     {  
         long currentValue = this.protocolHeader.CurrentValue;  
     }  
}  
```  
  
 <span data-ttu-id="d9544-240">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> 및 <xref:System.ServiceModel.MessageBodyMemberAttribute> 특성을 제공하여 서비스에서 보내고 받는 SOAP 메시지의 구조를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-240">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>  
  
```  
[DataContract]  
public class SomeProtocol  
{  
     [DataMember]  
     public long CurrentValue;  
     [DataMember]  
     public long Total;  
}  
  
[DataContract]  
public class Item  
{  
     [DataMember]  
     public string ItemNumber;  
     [DataMember]  
     public decimal Quantity;  
     [DataMember]  
     public decimal UnitPrice;  
}  
  
[MessageContract]  
public class ItemMesage  
{  
     [MessageHeader]  
     public SomeProtocol ProtocolHeader;  
     [MessageBody]  
     public Item Content;  
}  
  
[ServiceContract]  
public interface IItemService  
{  
     [OperationContract]  
     public void DeliverItem(ItemMessage itemMessage);  
}  
```  
  
 <span data-ttu-id="d9544-241">이 구문은 메시지 구조를 명시적으로 표현하지만 메시지 구조는 ASP.NET 웹 서비스의 코드로 암시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-241">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="d9544-242">또한 ASP.NET 구문에서는 메시지 헤더가 위 예제의 `ProtocolHeader` 속성과 같은 서비스 속성으로 나타나지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구문에서는 메시지 속성으로 더욱 정확하게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-242">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="d9544-243">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 끝점 구성에 메시지 헤더를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-243">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows message headers to be added to the configuration of endpoints.</span></span>  
  
```xml  
<service name="Service ">  
     <endpoint   
      address="EchoService"  
      binding="basicHttpBinding"  
      contract="IEchoService ">  
      <headers>  
      <dsig:X509Certificate   
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">  
       ...  
      </dsig:X509Certificate>  
      </headers>  
     </endpoint>  
</service>  
```  
  
 <span data-ttu-id="d9544-244">이 옵션을 사용하면 클라이언트 또는 서비스에 대한 코드에서 인프라 프로토콜 헤더를 참조할 필요가 없습니다. 끝점의 구성 방식에 따라 헤더가 메시지에 추가되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-244">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>  
  
## <a name="service-description"></a><span data-ttu-id="d9544-245">서비스 설명</span><span class="sxs-lookup"><span data-stu-id="d9544-245">Service Description</span></span>  
 <span data-ttu-id="d9544-246">쿼리 WSDL을 사용하여 ASP.NET 웹 서비스의 .asmx 파일에 대해 HTTP GET 요청을 발행하면 ASP.NET에서 해당 서비스를 설명하는 WSDL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-246">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="d9544-247">이 WSDL이 요청에 대한 응답으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-247">It returns that WSDL as the response to the request.</span></span>  
  
 <span data-ttu-id="d9544-248">ASP.NET 2.0을 통해 서비스가 WS-I(웹 서비스 상호 운용성) 조직의 Basic Profile 1.1과 호환되는지 확인하고 서비스가 WSDL과 호환된다는 클레임을 넣을 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-248">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="d9544-249">다음과 같이 `ConformsTo` 특성의 `EmitConformanceClaims` 및 <xref:System.Web.Services.WebServiceBindingAttribute> 매개 변수를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-249">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="d9544-250">ASP.NET에서 서비스에 대해 생성하는 WSDL을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-250">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="d9544-251"><xref:System.Web.Services.Description.ServiceDescriptionFormatExtension>의 파생 클래스를 만들어 WSDL에 항목을 추가함으로써 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-251">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>  
  
 <span data-ttu-id="d9544-252">IIS 5.1, 6.0 또는 WAS에서 호스트되는 HTTP 끝점이 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 .svc 파일에 대해 쿼리 WSDL을 사용하여 HTTP GET 요청을 발행하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 해당 서비스를 설명하는 WSDL로 응답하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-252">Issuing an HTTP GET request with the query WSDL for the .svc file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to respond with WSDL to describe the service.</span></span> <span data-ttu-id="d9544-253">httpGetEnabled가 true로 설정된 경우 .NET 응용 프로그램에서 호스트되는 서비스의 HTTP 기본 주소에 대해 쿼리 WSDL을 사용하여 HTTP GET 요청을 실행해도 동일한 효과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-253">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>  
  
 <span data-ttu-id="d9544-254">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 WS-MetadataExchange 요청에 대해서도 서비스를 설명하기 위해 생성하는 WSDL로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-254">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="d9544-255">ASP.NET 웹 서비스는 WS-MetadataExchange 요청에 대한 지원을 기본적으로 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-255">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>  
  
 <span data-ttu-id="d9544-256">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 생성하는 WSDL을 광범위하게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-256">The WSDL that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates can be extensively customized.</span></span> <span data-ttu-id="d9544-257"><xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스는 WSDL을 사용자 지정하기 위한 몇 가지 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-257">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="d9544-258">또한 WSDL을 생성하지 않고 지정된 URL에서 정적 WSDL 파일을 사용하도록 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DescriptionBehavior">  
     <metadataPublishing   
      enableMetadataExchange="true"   
      enableGetWsdl="true"   
      enableHelpPage="true"   
      metadataLocation=  
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>  
     </behavior>  
</behaviors>  
```  
  
## <a name="exception-handling"></a><span data-ttu-id="d9544-259">예외 처리</span><span class="sxs-lookup"><span data-stu-id="d9544-259">Exception Handling</span></span>  
 <span data-ttu-id="d9544-260">ASP.NET 웹 서비스에서 처리되지 않은 예외는 클라이언트에 SOAP 오류로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-260">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="d9544-261">또한 <xref:System.Web.Services.Protocols.SoapException> 클래스의 인스턴스를 명시적으로 throw하고 클라이언트에 전송되는 SOAP 오류의 내용을 세밀하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-261">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>  
  
 <span data-ttu-id="d9544-262">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서는 중요한 정보가 예외를 통해 실수로 노출되지 않도록, 처리되지 않은 예외를 클라이언트에 SOAP 오류로 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-262">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="d9544-263">디버깅을 위해 처리되지 않은 예외가 클라이언트에게 반환되도록 하는 구성 설정이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-263">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>  
  
 <span data-ttu-id="d9544-264">SOAP 오류를 클라이언트에게 반환하려면 데이터 계약 형식을 제네릭 형식으로 사용하여 제네릭 형식의 <xref:System.ServiceModel.FaultException%601> 인스턴스를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-264">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="d9544-265">또한 <xref:System.ServiceModel.FaultContractAttribute> 특성을 작업에 추가하여 작업에서 발생 가능한 오류를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-265">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>  
  
```  
[DataContract]  
public class MathFault  
{   
     [DataMember]  
     public string operation;  
     [DataMember]  
     public string problemType;  
}  
  
[ServiceContract]  
public interface ICalculator  
{  
     [OperationContract]  
     [FaultContract(typeof(MathFault))]  
     int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="d9544-266">이렇게 하면 가능한 오류가 서비스에 대한 WSDL에 알려지기 때문에 클라이언트 프로그래머가 작업에서 발생할 수 있는 오류를 정확히 예상하고 적절한 catch 문을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-266">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>  
  
```  
try  
{  
     result = client.Divide(value1, value2);  
}  
catch (FaultException<MathFault> e)  
{  
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "  
  + e.Detail.operation   
  + ". Problem: "   
  + e.Detail.problemType);  
}  
```  
  
## <a name="state-management"></a><span data-ttu-id="d9544-267">상태 관리</span><span class="sxs-lookup"><span data-stu-id="d9544-267">State Management</span></span>  
 <span data-ttu-id="d9544-268">ASP.NET 웹 서비스를 구현하는 데 사용되는 클래스는 <xref:System.Web.Services.WebService>에서 파생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-268">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>  
  
```  
public class Service : WebService, IEcho  
{  
  
 public string Echo(string input)  
 {  
  return input;  
 }  
}  
```  
  
 <span data-ttu-id="d9544-269">이러한 경우 <xref:System.Web.Services.WebService> 기본 클래스의 Context 속성을 사용하여 <xref:System.Web.HttpContext> 개체에 액세스하도록 클래스를 프로그래밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-269">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="d9544-270"><xref:System.Web.HttpContext> 개체를 사용하여 Application 속성을 통해 응용 프로그램 상태 정보를 업데이트 및 검색하고 Session 속성을 통해 세션 상태 정보를 업데이트 및 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-270">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>  
  
 <span data-ttu-id="d9544-271">ASP.NET에서는 <xref:System.Web.HttpContext>의 Session 속성을 사용하여 액세스되는 세션 상태 정보가 실제로 저장되는 위치를 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-271">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="d9544-272">세션 상태 정보는 쿠키, 데이터베이스, 현재 서버의 메모리 또는 지정된 서버의 메모리에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-272">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="d9544-273">저장 위치는 서비스의 구성 파일에서 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-273">The choice is made in the service’s configuration file.</span></span>  
  
 <span data-ttu-id="d9544-274">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 상태 관리를 위한 확장 가능한 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides extensible objects for state management.</span></span> <span data-ttu-id="d9544-275">확장 가능한 개체는 <xref:System.ServiceModel.IExtensibleObject%601>를 구현하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-275">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="d9544-276">가장 중요한 확장 가능한 개체는 <xref:System.ServiceModel.ServiceHostBase> 및 <xref:System.ServiceModel.InstanceContext>입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-276">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="d9544-277">`ServiceHostBase`를 사용하면 같은 호스트에 있는 모든 서비스 유형의 모든 인스턴스에서 액세스할 수 있는 상태를 유지할 수 있으며, `InstanceContext`를 사용하면 서비스 유형의 같은 인스턴스 내에서 실행되는 코드로 액세스할 수 있는 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-277">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>  
  
 <span data-ttu-id="d9544-278">여기서 `TradingSystem` 서비스 유형에는 같은 <xref:System.ServiceModel.ServiceBehaviorAttribute> 클라이언트 인스턴스의 모든 호출이 서비스 유형의 같은 인스턴스로 라우트되도록 지정하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-278">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client instance are routed to the same instance of the service type.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class TradingSystem: ITradingService  
```  
  
 <span data-ttu-id="d9544-279">`DealData` 클래스는 서비스 유형의 같은 인스턴스 내에서 실행되는 코드로 액세스할 수 있는 상태를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-279">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>  
  
```  
internal class DealData: IExtension<InstanceContext>  
{  
 public string DealIdentifier = null;  
 public Trade[] Trades = null;  
}  
```  
  
 <span data-ttu-id="d9544-280">서비스 계약의 작업 중 하나를 구현하는 서비스 유형의 코드에서 `DealData` 상태 개체는 서비스 유형의 현재 인스턴스에 대한 상태에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-280">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>  
  
```  
string ITradingService.BeginDeal()  
{  
 string dealIdentifier = Guid.NewGuid().ToString();  
 DealData state = new DealData(dealIdentifier);  
 OperationContext.Current.InstanceContext.Extensions.Add(state);  
 return dealIdentifier;  
}  
```  
  
 <span data-ttu-id="d9544-281">그런 다음 이 상태 개체는 서비스 계약의 작업 중 다른 하나를 구현하는 코드로 검색하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-281">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>  
  
```  
void ITradingService.AddTrade(Trade trade)  
{  
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();  
 dealData.AddTrade(trade);  
}  
```  
  
 <span data-ttu-id="d9544-282">ASP.NET에서 <xref:System.Web.HttpContext> 클래스의 상태 정보가 실제로 저장되는 위치를 제어할 수 있지만, 적어도 초기 버전의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 확장 가능한 개체가 저장되는 위치를 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-282">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="d9544-283">이러한 점이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 위해 ASP.NET 호환 모드를 선택하는 가장 정당한 이유가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-283">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="d9544-284">구성 가능한 상태 관리가 필수적인 경우 ASP.NET 호환 모드를 채택함으로써 <xref:System.Web.HttpContext> 클래스의 기능을 ASP.NET에서와 똑같은 방식으로 사용할 수 있으며 <xref:System.Web.HttpContext> 클래스를 사용하여 관리되는 상태 정보가 저장되는 위치를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-284">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>  
  
## <a name="security"></a><span data-ttu-id="d9544-285">보안</span><span class="sxs-lookup"><span data-stu-id="d9544-285">Security</span></span>  
 <span data-ttu-id="d9544-286">ASP.NET 웹 서비스의 보안을 유지하기 위한 옵션은 IIS 응용 프로그램의 보안을 유지하는 옵션과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-286">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="d9544-287">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램은 IIS뿐만 아니라 .NET 실행 파일 내에서도 호스트될 수 있기 때문에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램의 보안을 유지하기 위한 옵션은 IIS 기능과 별도로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-287">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can be hosted not only within IIS but also within any .NET executable, the options for securing [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="d9544-288">그러나 ASP.NET 웹 서비스에 제공되는 기능은 ASP.NET 호환 모드에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-288">However, the facilities provided for ASP.NET Web services are also available for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-authentication"></a><span data-ttu-id="d9544-289">보안: 인증</span><span class="sxs-lookup"><span data-stu-id="d9544-289">Security: Authentication</span></span>  
 <span data-ttu-id="d9544-290">IIS는 응용 프로그램에 대한 액세스를 제어하는 기능을 제공하므로 이 기능을 통해 Windows 인증, 다이제스트 인증, 기본 인증, .NET Passport 인증 등 다양한 모드의 인증을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-290">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="d9544-291">Windows 인증 옵션을 사용하면 ASP.NET 웹 서비스에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-291">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="d9544-292">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램이 IIS 내에서 호스트되는 경우에는 이 응용 프로그램에 대한 익명 액세스를 허용하도록 IIS를 구성하여 다양한 다른 옵션과 함께 Windows 인증을 지원하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 자체에서 인증을 관리할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-292">However, when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="d9544-293">기본 제공되는 다른 옵션으로는 사용자 이름 토큰, X.509 인증서, SAML 토큰, CardSpace 카드 등이 있으며 사용자 지정 인증 메커니즘을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-293">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>  
  
### <a name="security-impersonation"></a><span data-ttu-id="d9544-294">보안: 가장</span><span class="sxs-lookup"><span data-stu-id="d9544-294">Security: Impersonation</span></span>  
 <span data-ttu-id="d9544-295">ASP.NET에서는 ASP.NET 웹 서비스가 특정 사용자로, 또는 현재 요청에서 제공된 사용자의 자격 증명으로 가장할 수 있도록 하는 ID 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-295">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="d9544-296">이 요소를 사용하면 ASP.NET 호환 모드에서 실행되고 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 가장을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-296">That element can be used to configure impersonation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications running in ASP.NET compatibility mode.</span></span>  
  
 <span data-ttu-id="d9544-297">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 시스템은 가장할 특정 사용자를 지정하기 위한 자체 ID 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="d9544-298">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 및 서비스는 가장을 위해 별도로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-298">Also, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="d9544-299">클라이언트는 요청을 전송할 때 현재 사용자로 가장하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-299">Clients can be configured to impersonate the current user when they transmit requests.</span></span>  
  
```xml  
<behaviors>  
     <behavior name="DerivativesCalculatorClientBehavior">  
      <clientCredentials>  
      <windows allowedImpersonationLevel="Impersonation"/>  
      </clientCredentials>  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="d9544-300">서비스 작업은 현재 요청에서 제공된 사용자의 자격 증명으로 가장하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-300">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public void Receive(Message input)  
```  
  
### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="d9544-301">보안: 액세스 제어 목록을 사용하여 권한 부여</span><span class="sxs-lookup"><span data-stu-id="d9544-301">Security: Authorization using Access Control Lists</span></span>  
 <span data-ttu-id="d9544-302">ACL(액세스 제어 목록)을 사용하면 .asmx 파일에 대한 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-302">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="d9544-303">그러나 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .svc 파일에 대한 ACL은 ASP.NET 호환 모드인 경우를 제외하고는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-303">However, ACLs on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .svc files are ignored except in ASP.NET compatibility mode.</span></span>  
  
### <a name="security-role-based-authorization"></a><span data-ttu-id="d9544-304">보안: 역할 기반 권한 부여</span><span class="sxs-lookup"><span data-stu-id="d9544-304">Security: Role-based Authorization</span></span>  
 <span data-ttu-id="d9544-305">IIS Windows 인증 옵션을 ASP.NET 구성 언어로 제공되는 권한 부여 요소와 함께 사용하면 사용자에게 지정된 Windows 그룹 기반의 ASP.NET 웹 서비스에 대한 역할 기반 권한을 쉽게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-305">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="d9544-306">ASP.NET 2.0에는 더 포괄적인 역할 기반 권한 부여 메커니즘인 역할 공급자가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-306">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>  
  
 <span data-ttu-id="d9544-307">역할 공급자는 사용자에게 할당된 역할을 쿼리하기 위한 기본 인터페이스를 구현하는 클래스입니다. 각 역할 공급자는 서로 다른 소스에서 해당 정보를 검색하는 방법을 인식하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-307">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="d9544-308">ASP.NET 2.0은 Microsoft SQL Server 데이터베이스에서 역할 할당을 검색할 수 있는 역할 공급자와 Windows Server 2003 권한 부여 관리자에서 역할 할당을 검색할 수 있는 역할 공급자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-308">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>  
  
 <span data-ttu-id="d9544-309">실제로 역할 공급자 메커니즘은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 포함한 모든 .NET 응용 프로그램에서 ASP.NET과 별도로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-309">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="d9544-310">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 대한 다음 샘플 구성에서는 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>를 통해 ASP.NET 역할 공급자를 사용하는 옵션이 선택되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-310">The following sample configuration for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
     <services>  
         <service name="Service.ResourceAccessServiceType"   
             behaviorConfiguration="ServiceBehavior">  
             <endpoint   
              address="ResourceAccessService"   
              binding="wsHttpBinding"   
              contract="Service.IResourceAccessContract"/>  
         </service>  
     </services>  
     <behaviors>  
       <behavior name="ServiceBehavior">  
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>  
      </behavior>  
     </behaviors>  
</system.serviceModel>  
```  
  
### <a name="security-claims-based-authorization"></a><span data-ttu-id="d9544-311">보안: 클레임 기반 권한 부여</span><span class="sxs-lookup"><span data-stu-id="d9544-311">Security: Claims-based Authorization</span></span>  
 <span data-ttu-id="d9544-312">클레임에 기반하여 보호되는 리소스에 대한 액세스 권한 부여를 완벽하게 지원하는 것은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 가장 중요한 혁신 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-312">One of the most important innovations of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="d9544-313">클레임은 형식, 권한 및 값으로 구성됩니다. 예를 들어, 운전 면허증을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d9544-313">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="d9544-314">운전 면허증은 소지인에 대한 클레임 집합으로 구성되는데, 그 중 하나는 소지인의 생년월일입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-314">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="d9544-315">이 클레임의 형식은 생년월일이고, 값은 운전자의 생년월일입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-315">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="d9544-316">클레임이 소지인에게 부여하는 권한은 소지인이 클레임 값으로 수행할 수 있는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-316">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="d9544-317">운전자의 생년월일에 대한 클레임의 경우 권한은 단순한 소유입니다. 운전자는 해당 생년월일을 소유하고 있지만 변경하는 등의 작업은 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-317">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="d9544-318">역할은 단순히 클레임의 한 형식이기 때문에 클레임 기반 인증은 역할 기반 인증을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-318">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>  
  
 <span data-ttu-id="d9544-319">클레임 기반 인증은 클레임 집합을 작업의 액세스 요구 사항과 비교하여 그 결과에 따라 작업에 대한 액세스 권한을 부여하거나 거부함으로써 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-319">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="d9544-320">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `ServiceAuthorizationManager`의 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 속성에 값을 다시 한 번 할당함으로써 클레임 기반 권한 부여를 실행하는 데 사용할 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-320">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>  
  
```xml  
<behaviors>  
     <behavior name='ServiceBehavior'>  
     <serviceAuthorization   
     serviceAuthorizationManagerType=  
                   'Service.AccessChecker, Service' />  
     </behavior>  
</behaviors>  
```  
  
 <span data-ttu-id="d9544-321">클레임 기반 권한 부여를 실행하는 데 사용되는 클래스는 <xref:System.ServiceModel.ServiceAuthorizationManager>에서 파생되어야 하며, 여기서 `AccessCheck()` 메서드만 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-321">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d9544-322">에서는 서비스 작업이 호출될 때마다 이 메서드를 호출하여 <xref:System.ServiceModel.OperationContext> 개체를 제공하며, 이 개체의 `ServiceSecurityContext.AuthorizationContext` 속성에는 사용자에 대한 클레임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-322"> calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d9544-323">는 사용자가 인증을 위해 제공한 보안 토큰으로부터 사용자에 대한 클레임을 조합하는 작업을 수행하므로 이러한 클레임이 해당 작업에 충분한지 여부를 평가하는 간단한 작업만 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-323"> does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>  
  
 <span data-ttu-id="d9544-324">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 모든 종류의 보안 토큰으로부터 클레임을 자동으로 조합합니다. 그러면 클레임 기반 권한 부여 코드가 인증 메커니즘으로부터 완전히 독립되므로 이는 매우 중요한 혁신 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-324">That [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="d9544-325">반면 ASP.NET에서 ACL 또는 역할을 사용하는 권한 부여는 Windows 인증과 밀접하게 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-325">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>  
  
### <a name="security-confidentiality"></a><span data-ttu-id="d9544-326">보안: 기밀성</span><span class="sxs-lookup"><span data-stu-id="d9544-326">Security: Confidentiality</span></span>  
 <span data-ttu-id="d9544-327">IIS에서 응용 프로그램이 HTTPS(Secure Hypertext Transfer Protocol)를 사용하도록 구성하여 ASP.NET 웹 서비스와 교환되는 메시지의 기밀성을 전송 수준에서 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-327">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="d9544-328">IIS에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에 대해서도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-328">The same can be done for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted within IIS.</span></span> <span data-ttu-id="d9544-329">IIS 외부에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램도 보안 전송 프로토콜을 사용하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-329">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="d9544-330">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 WS-Security 프로토콜을 사용하여 메시지가 전송되기 전에 보안하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-330">More important, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="d9544-331">WS-Security를 사용하여 메시지 본문의 보안을 유지하면 메시지가 최종 목적지에 도달하기 전에 중간 단계를 통해 기밀 상태로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-331">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>  
  
## <a name="globalization"></a><span data-ttu-id="d9544-332">전역화</span><span class="sxs-lookup"><span data-stu-id="d9544-332">Globalization</span></span>  
 <span data-ttu-id="d9544-333">ASP.NET 구성 언어를 사용하여 개별 서비스의 문화권을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-333">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="d9544-334">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 ASP.NET 호환 모드인 경우를 제외하고 이러한 구성 설정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-334">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="d9544-335">ASP.NET 호환 모드를 사용하지 않는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 지역화하려면 서비스 유형을 문화권별 어셈블리로 컴파일하고 각 문화권별 어셈블리가 별도의 문화권별 끝점을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9544-335">To localize a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9544-336">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9544-336">See Also</span></span>  
 [<span data-ttu-id="d9544-337">WCF 기반 의도적으로 사용 되는 표준을 ASP.NET 웹 서비스 비교</span><span class="sxs-lookup"><span data-stu-id="d9544-337">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
