---
title: 서비스 계약에서 데이터 전송 지정
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
caps.latest.revision: 38
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc64ff14c321bd2053b0a97b3cf1ac075b02e973
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="specifying-data-transfer-in-service-contracts"></a><span data-ttu-id="7d43c-102">서비스 계약에서 데이터 전송 지정</span><span class="sxs-lookup"><span data-stu-id="7d43c-102">Specifying Data Transfer in Service Contracts</span></span>
<span data-ttu-id="7d43c-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 메시징 인프라로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] can be thought of as a messaging infrastructure.</span></span> <span data-ttu-id="7d43c-104">서비스 작업에서는 메시지를 받고 처리한 다음 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-104">Service operations can receive messages, process them, and send them messages.</span></span> <span data-ttu-id="7d43c-105">메시지는 작업 계약을 사용하여 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-105">Messages are described using operation contracts.</span></span> <span data-ttu-id="7d43c-106">다음 계약을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-106">For example, consider the following contract.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(string fromCity, string toCity);  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
  
    <OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
End Interface  
```  
  
 <span data-ttu-id="7d43c-107">여기서 `GetAirfare` 작업은 `fromCity` 및 `toCity`에 대한 정보가 있는 메시지를 수락한 다음 숫자가 포함된 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-107">Here, the `GetAirfare` operation accepts a message with information about `fromCity` and `toCity`, and then returns a message that contains a number.</span></span>  
  
 <span data-ttu-id="7d43c-108">이 항목에서는 작업 계약에서 메시지를 설명할 수 있는 여러 가지 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-108">This topic explains the various ways in which an operation contract can describe messages.</span></span>  
  
## <a name="describing-messages-by-using-parameters"></a><span data-ttu-id="7d43c-109">매개 변수를 사용하여 메시지 설명</span><span class="sxs-lookup"><span data-stu-id="7d43c-109">Describing Messages by Using Parameters</span></span>  
 <span data-ttu-id="7d43c-110">메시지를 설명하는 가장 간단한 방법은 매개 변수 목록과 반환 값을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-110">The simplest way to describe a message is to use a parameter list and the return value.</span></span> <span data-ttu-id="7d43c-111">앞의 예제에서 `fromCity` 및 `toCity` 문자열 매개 변수는 요청 메시지를 설명하는 데 사용되었고 float 반환 값은 회신 메시지를 설명하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-111">In the preceding example, the `fromCity` and `toCity` string parameters were used to describe the request message, and the float return value was used to describe the reply message.</span></span> <span data-ttu-id="7d43c-112">반환 값으로만 회신 메시지를 설명할 수 없는 경우에는 out 매개 변수를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-112">If the return value alone is not enough to describe a reply message, out parameters may be used.</span></span> <span data-ttu-id="7d43c-113">예를 들어, 다음 연산의 경우 요청 메시지에는 `fromCity` 및 `toCity`가 있으며 회신 메시지에는 통화와 숫자가 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-113">For example, the following operation has `fromCity` and `toCity` in its request message, and a number together with a currency in its reply message:</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 <span data-ttu-id="7d43c-114">또한 참조 매개 변수를 사용하여 요청 및 회신 메시지의 매개 변수 부분을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-114">Additionally, you may use reference parameters to make a parameter part of both the request and the reply message.</span></span> <span data-ttu-id="7d43c-115">매개 변수는 serialize할 수 있는, 즉 XML로 변환할 수 있는 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-115">The parameters must be of types that can be serialized (converted to XML).</span></span> <span data-ttu-id="7d43c-116">기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스라고 하는 구성 요소를 사용하여 이 변환을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-116">By default, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a component called the <xref:System.Runtime.Serialization.DataContractSerializer> class to perform this conversion.</span></span> <span data-ttu-id="7d43c-117">`int`, `string`, `float` 및 `DateTime`과 같은 가장 기본적인 형식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-117">Most primitive types (such as `int`, `string`, `float`, and `DateTime`.) are supported.</span></span> <span data-ttu-id="7d43c-118">사용자 정의 형식에는 일반적으로 데이터 계약이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-118">User-defined types must normally have a data contract.</span></span> <span data-ttu-id="7d43c-119">자세한 내용은 참조 [를 사용 하 여 데이터 계약](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-119">For more information, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
```csharp
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
  
    [DataContract]  
    public class Itinerary  
    {  
        [DataMember]  
        public string fromCity;  
        [DataMember]  
        public string toCity;  
   }  
}  
```  
  
```vb  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
    <DataContract()>  
    Class Itinerary  
  
        <DataMember()>  
        Public fromCity As String  
        <DataMember()>  
        Public toCity As String  
    End Class  
End Interface  
```  
  
 <span data-ttu-id="7d43c-120">`DataContractSerializer`는 사용자의 형식을 serialize하기에 적합하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-120">Occasionally, the `DataContractSerializer` is not adequate to serialize your types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7d43c-121">에서는 대체 serialization 엔진인 <xref:System.Xml.Serialization.XmlSerializer>를 지원하므로, 이 엔진을 사용하여 매개 변수를 serialize할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-121"> supports an alternative serialization engine, the <xref:System.Xml.Serialization.XmlSerializer>, which you can also use to serialize parameters.</span></span> <span data-ttu-id="7d43c-122"><xref:System.Xml.Serialization.XmlSerializer>를 통해 `XmlAttributeAttribute`와 같은 특성을 사용하여 결과 XML을 보다 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-122">The <xref:System.Xml.Serialization.XmlSerializer> allows you to use more control over the resultant XML using attributes such as the `XmlAttributeAttribute`.</span></span> <span data-ttu-id="7d43c-123">특정 연산이나 전체 서비스에 <xref:System.Xml.Serialization.XmlSerializer>를 사용하려면 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 특성을 연산이나 서비스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-123">To switch to using the <xref:System.Xml.Serialization.XmlSerializer> for a particular operation or for the entire service, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to an operation or a service.</span></span> <span data-ttu-id="7d43c-124">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="7d43c-124">For example:</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    [XmlSerializerFormat]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
}  
public class Itinerary  
{  
    public string fromCity;  
    public string toCity;  
    [XmlAttribute]  
    public bool isFirstClass;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    <XmlSerializerFormat>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
End Interface  
  
Class Itinerary  
  
    Public fromCity As String  
    Public toCity As String  
    <XmlSerializerFormat()>  
    Public isFirstClass As Boolean  
End Class  
```  
  
 <span data-ttu-id="7d43c-125">자세한 내용은 참조 [XmlSerializer 클래스를 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-125">For more information, see [Using the XmlSerializer Class](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span></span> <span data-ttu-id="7d43c-126">위 항목에 설명된 대로 수동으로 <xref:System.Xml.Serialization.XmlSerializer>로 전환할 특별한 이유가 없는 한 이 예제에서처럼 수동으로 전환하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-126">Remember that manually switching to the <xref:System.Xml.Serialization.XmlSerializer> as shown here is not recommended unless you have specific reasons to do so as detailed in that topic.</span></span>  
  
 <span data-ttu-id="7d43c-127">.NET 매개 변수 이름을 계약 이름으로부터 격리시키려면 <xref:System.ServiceModel.MessageParameterAttribute> 특성을 사용하고, `Name` 속성을 사용하여 계약 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-127">To isolate .NET parameter names from contract names, you can use the <xref:System.ServiceModel.MessageParameterAttribute> attribute, and use the `Name` property to set the contract name.</span></span> <span data-ttu-id="7d43c-128">예를 들면, 다음 작업 계약은 이 항목의 첫 번째 예제에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-128">For example, the following operation contract is equivalent to the first example in this topic.</span></span>  
  
```csharp  
[OperationContract]  
public float GetAirfare(  
    [MessageParameter(Name="fromCity")] string originCity,  
    [MessageParameter(Name="toCity")] string destinationCity);  
```  
  
```vb  
<OperationContract()>  
  Function GetAirfare(<MessageParameter(Name := "fromCity")> fromCity As String, <MessageParameter(Name := "toCity")> toCity As String) As Double  
```  
  
## <a name="describing-empty-messages"></a><span data-ttu-id="7d43c-129">빈 메시지 설명</span><span class="sxs-lookup"><span data-stu-id="7d43c-129">Describing Empty Messages</span></span>  
 <span data-ttu-id="7d43c-130">빈 요청 메시지는 입력 매개 변수나 참조 매개 변수를 사용하지 않고 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-130">An empty request message can be described by having no input or reference parameters.</span></span> <span data-ttu-id="7d43c-131">예를 들어 C#의 경우:</span><span class="sxs-lookup"><span data-stu-id="7d43c-131">For example in C#:</span></span>  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 <span data-ttu-id="7d43c-132">예를 들어 VB의 경우:</span><span class="sxs-lookup"><span data-stu-id="7d43c-132">For example in VB:</span></span>  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 <span data-ttu-id="7d43c-133">빈 회신 메시지는 출력 또는 참조 매개 변수 없이 `void` 반환 형식을 사용하여 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-133">An empty reply message can be described by having a `void` return type and no output or reference parameters.</span></span> <span data-ttu-id="7d43c-134">예:</span><span class="sxs-lookup"><span data-stu-id="7d43c-134">For example in:</span></span>  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 <span data-ttu-id="7d43c-135">이것은 다음과 같은 단방향 연산과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-135">This is different from a one-way operation, such as:</span></span>  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 <span data-ttu-id="7d43c-136">`SetTemperatureStatus` 연산은 빈 메시지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-136">The `SetTemperatureStatus` operation returns an empty message.</span></span> <span data-ttu-id="7d43c-137">입력 메시지를 처리하는 데 문제가 있을 경우 대신 오류를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-137">It may return a fault instead if there is a problem processing the input message.</span></span> <span data-ttu-id="7d43c-138">`SetLightbulbStatus` 연산은 아무 것도 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-138">The `SetLightbulbStatus` operation returns nothing.</span></span> <span data-ttu-id="7d43c-139">이 연산에서 오류 조건을 전달할 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-139">There is no way to communicate a fault condition from this operation.</span></span>  
  
## <a name="describing-messages-by-using-message-contracts"></a><span data-ttu-id="7d43c-140">메시지 계약을 사용하여 메시지 설명</span><span class="sxs-lookup"><span data-stu-id="7d43c-140">Describing Messages by Using Message Contracts</span></span>  
 <span data-ttu-id="7d43c-141">하나의 형식을 사용하여 전체 메시지를 나타내야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-141">You may want to use a single type to represent the entire message.</span></span> <span data-ttu-id="7d43c-142">이러한 목적을 위해 데이터 계약을 사용할 수는 있지만 메시지 계약을 사용하는 것이 좋습니다. 이렇게 하면 결과 XML에서 불필요한 래핑 수준이 생기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-142">While it is possible to use a data contract for this purpose, the recommended way to do this is to use a message contract—this avoids unnecessary levels of wrapping in the resultant XML.</span></span> <span data-ttu-id="7d43c-143">또한 메시지 계약을 통해 결과 메시지를 보다 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-143">Additionally, message contracts allow you to exercise more control over resultant messages.</span></span> <span data-ttu-id="7d43c-144">예를 들어 메시지 본문에 필요한 정보와 메시지 헤더에 필요한 사항을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-144">For instance, you can decide which pieces of information should be in the message body and which should be in the message headers.</span></span> <span data-ttu-id="7d43c-145">다음 예제에서는 메시지 계약을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-145">The following example shows the use of message contracts.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    GetAirfareResponse GetAirfare(GetAirfareRequest request);  
}  
  
[MessageContract]  
public class GetAirfareRequest  
{  
    [MessageHeader] public DateTime date;  
    [MessageBodyMember] public Itinerary itinerary;  
}  
  
[MessageContract]  
public class GetAirfareResponse  
{  
    [MessageBodyMember] public float airfare;  
    [MessageBodyMember] public string currency;  
}  
  
[DataContract]  
public class Itinerary  
{  
    [DataMember] public string fromCity;  
    [DataMember] public string toCity;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    Function GetAirfare(request As GetAirfareRequest) As GetAirfareResponse  
End Interface  
  
<MessageContract()>  
Public Class GetAirfareRequest  
    <MessageHeader()>   
    Public Property date as DateTime  
    <MessageBodyMember()>  
    Public Property itinerary As Itinerary  
End Class  
  
<MessageContract()>  
Public Class GetAirfareResponse  
    <MessageBodyMember()>  
    Public Property airfare As Double  
    <MessageBodyMember()> Public Property currency As String  
End Class  
  
<DataContract()>  
Public Class Itinerary  
    <DataMember()> Public Property fromCity As String  
    <DataMember()> Public Property toCity As String  
End Class  
```  
  
 <span data-ttu-id="7d43c-146">자세한 내용은 참조 [메시지 계약을 사용 하 여](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-146">For more information, see [Using Message Contracts](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
 <span data-ttu-id="7d43c-147">앞의 예제의 경우 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-147">In the previous example, the <xref:System.Runtime.Serialization.DataContractSerializer> class is still used by default.</span></span> <span data-ttu-id="7d43c-148"><xref:System.Xml.Serialization.XmlSerializer> 클래스는 메시지 계약에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-148">The <xref:System.Xml.Serialization.XmlSerializer> class can also be used with message contracts.</span></span> <span data-ttu-id="7d43c-149">이 작업을 수행하려면 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 특성을 연산이나 계약에 적용하고 메시지 헤더와 본문 멤버의 <xref:System.Xml.Serialization.XmlSerializer> 클래스와 호환되는 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-149">To do this, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to either the operation or the contract, and use types compatible with the <xref:System.Xml.Serialization.XmlSerializer> class in the message headers and body members.</span></span>  
  
## <a name="describing-messages-by-using-streams"></a><span data-ttu-id="7d43c-150">스트림을 사용하여 메시지 설명</span><span class="sxs-lookup"><span data-stu-id="7d43c-150">Describing Messages by Using Streams</span></span>  
 <span data-ttu-id="7d43c-151">연산에서 메시지를 설명하는 또 다른 방법은 <xref:System.IO.Stream> 클래스 또는 작업 계약의 파생 클래스 중 하나를 사용하거나 메시지 계약 본문 멤버(이 경우 유일한 멤버여야 함)로 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-151">Another way to describe messages in operations is to use the <xref:System.IO.Stream> class or one of its derived classes in an operation contract or as a message contract body member (it must be the only member in this case).</span></span> <span data-ttu-id="7d43c-152">들어오는 메시지의 경우 형식은 `Stream`이어야 하며, 파생 클래스는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-152">For incoming messages, the type must be `Stream`—you cannot use derived classes.</span></span>  
  
 <span data-ttu-id="7d43c-153">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 serializer를 호출하지 않는 대신, 스트림에서 데이터를 검색하여 보내는 메시지에 직접 넣거나 들어오는 메시지에서 데이터를 검색하여 스트림에 직접 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-153">Instead of invoking the serializer, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] retrieves data from a stream and puts it directly into an outgoing message, or retrieves data from an incoming message and puts it directly into a stream.</span></span> <span data-ttu-id="7d43c-154">다음 예제에서는 스트림의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-154">The following sample shows the use of streams.</span></span>  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 <span data-ttu-id="7d43c-155">하나의 메시지 본문에서 `Stream`과 비스트림 데이터를 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-155">You cannot combine `Stream` and non-stream data in a single message body.</span></span> <span data-ttu-id="7d43c-156">메시지 헤더에 추가 데이터를 넣으려면 메시지 계약을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-156">Use a message contract to put the extra data in message headers.</span></span> <span data-ttu-id="7d43c-157">다음 예제에서는 작업 계약을 정의할 때 잘못된 스트림 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-157">The following example shows the incorrect usage of streams when defining the operation contract.</span></span>  
  
```csharp  
//Incorrect:  
// [OperationContract]  
// public void UploadFile (string fileName, Stream fileData);  
```  
  
```vb  
'Incorrect:  
    '<OperationContract()>  
    Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
```  
  
 <span data-ttu-id="7d43c-158">다음 샘플에서는 작업 계약을 정의할 때 올바른 스트림 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-158">The following sample shows the correct usage of streams when defining an operation contract.</span></span>  
  
```csharp  
[OperationContract]  
public void UploadFile (UploadFileMessage message);  
//code omitted  
[MessageContract]  
public class UploadFileMessage  
{  
    [MessageHeader] public string fileName;  
    [MessageBodyMember] public Stream fileData;  
}  
```  
  
```vb  
<OperationContract()>  
Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
'Code Omitted  
<MessageContract()>  
Public Class UploadFileMessage  
   <MessageHeader()>  
    Public Property fileName As String  
    <MessageBodyMember()>  
    Public Property fileData As Stream  
End Class  
```  
  
 <span data-ttu-id="7d43c-159">자세한 내용은 참조 [큰 데이터 및 스트리밍](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-159">For more information, see [Large Data and Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="using-the-message-class"></a><span data-ttu-id="7d43c-160">Message 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="7d43c-160">Using the Message Class</span></span>  
 <span data-ttu-id="7d43c-161">보내거나 받은 메시지를 프로그래밍 방식으로 완벽하게 제어하려면 다음 예제 코드에서처럼 <xref:System.ServiceModel.Channels.Message> 클래스를 직접 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-161">To have complete programmatic control over messages sent or received, you can use the <xref:System.ServiceModel.Channels.Message> class directly, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 <span data-ttu-id="7d43c-162">이 고급 시나리오에 자세하게에서 설명 [메시지 클래스를 사용 하 여](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-162">This is an advanced scenario, which is described in detail in [Using the Message Class](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).</span></span>  
  
## <a name="describing-fault-messages"></a><span data-ttu-id="7d43c-163">오류 메시지 설명</span><span class="sxs-lookup"><span data-stu-id="7d43c-163">Describing Fault Messages</span></span>  
 <span data-ttu-id="7d43c-164">반환 값과 출력 또는 참조 매개 변수를 사용하여 설명하는 메시지 이외에, 단방향이 아닌 연산은 적어도 두 개의 메시지, 즉 일반 응답 메시지와 오류 메시지를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-164">In addition to the messages that are described by the return value and output or reference parameters, any operation that is not one-way can return at least two possible messages: its normal response message and a fault message.</span></span> <span data-ttu-id="7d43c-165">다음 작업 계약을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-165">Consider the following operation contract.</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 <span data-ttu-id="7d43c-166">이 연산은 `float` 숫자가 포함된 일반 메시지 또는 오류 코드 및 설명이 포함된 오류 메시지를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-166">This operation may either return a normal message that contains a `float` number, or a fault message that contains a fault code and a description.</span></span> <span data-ttu-id="7d43c-167">서비스 구현에서 <xref:System.ServiceModel.FaultException>을 throw하여 이 연산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-167">You can accomplish this by throwing a <xref:System.ServiceModel.FaultException> in your service implementation.</span></span>  
  
 <span data-ttu-id="7d43c-168"><xref:System.ServiceModel.FaultContractAttribute> 특성을 사용하여 가능한 추가 오류 메시지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-168">You can specify additional possible fault messages by using the <xref:System.ServiceModel.FaultContractAttribute> attribute.</span></span> <span data-ttu-id="7d43c-169">추가 오류는 다음 예제 코드에서처럼 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 serialize할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-169">The additional faults must be serializable using the <xref:System.Runtime.Serialization.DataContractSerializer>, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
[FaultContract(typeof(ItineraryNotAvailableFault))]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
  
//code omitted  
  
[DataContract]  
public class ItineraryNotAvailableFault  
{  
    [DataMember]  
    public bool IsAlternativeDateAvailable;  
  
    [DataMember]  
    public DateTime alternativeSuggestedDate;  
}  
```  
  
```vb  
<OperationContract()>  
<FaultContract(GetType(ItineraryNotAvailableFault))>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime) As Double  
  
'Code Omitted  
<DataContract()>  
Public Class  
  <DataMember()>  
  Public Property IsAlternativeDateAvailable As Boolean  
  <DataMember()>  
  Public Property alternativeSuggestedDate As DateTime  
End Class  
```  
  
 <span data-ttu-id="7d43c-170">이러한 추가 오류는 해당하는 데이터 계약 형식의 <xref:System.ServiceModel.FaultException%601>을 throw하여 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-170">These additional faults can be generated by throwing a <xref:System.ServiceModel.FaultException%601> of the appropriate data contract type.</span></span> <span data-ttu-id="7d43c-171">자세한 내용은 참조 [예외 처리 및 오류](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-171">For more information, see [Handling Exceptions and Faults](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span></span>  
  
 <span data-ttu-id="7d43c-172"><xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 오류를 설명할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-172">You cannot use the <xref:System.Xml.Serialization.XmlSerializer> class to describe faults.</span></span> <span data-ttu-id="7d43c-173"><xref:System.ServiceModel.XmlSerializerFormatAttribute>는 오류 계약에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-173">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> has no effect on fault contracts.</span></span>  
  
## <a name="using-derived-types"></a><span data-ttu-id="7d43c-174">파생 형식 사용</span><span class="sxs-lookup"><span data-stu-id="7d43c-174">Using Derived Types</span></span>  
 <span data-ttu-id="7d43c-175">특정 연산 또는 메시지 계약에 기본 형식을 사용한 다음 실제로 연산을 호출할 때는 파생 형식을 사용해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-175">You may want to use a base type in an operation or a message contract, and then use a derived type when actually invoking the operation.</span></span> <span data-ttu-id="7d43c-176">이 경우 파생 형식을 사용할 수 있도록 <xref:System.ServiceModel.ServiceKnownTypeAttribute> 특성 또는 일부 대체 메커니즘을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-176">In this case, you must use either the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute or some alternative mechanism to allow the use of derived types.</span></span> <span data-ttu-id="7d43c-177">다음 연산을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-177">Consider the following operation.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 <span data-ttu-id="7d43c-178">`Book` 및 `Magazine` 이 두 형식이 `LibraryItem`에서 파생된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-178">Assume that two types, `Book` and `Magazine`, derive from `LibraryItem`.</span></span> <span data-ttu-id="7d43c-179">이 형식을 `IsLibraryItemAvailable` 연산에서 사용하려면 다음과 같이 연산을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-179">To use these types in the `IsLibraryItemAvailable` operation, you can change the operation as follows:</span></span>  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 <span data-ttu-id="7d43c-180">또는 다음 예제 코드에서처럼 기본 <xref:System.Runtime.Serialization.KnownTypeAttribute>가 사용 중인 경우 <xref:System.Runtime.Serialization.DataContractSerializer> 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-180">Alternatively, you can use the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute when the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
  
// code omitted   
  
[DataContract]  
[KnownType(typeof(Book))]  
[KnownType(typeof(Magazine))]  
public class LibraryItem  
{  
    //code omitted  
}  
```  
  
```vb  
<OperationContract()>  
Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
  
'Code Omitted  
<DataContract()>  
<KnownType(GetType(Book))>  
<KnownType(GetType(Magazine))>  
Public Class LibraryItem  
  'Code Omitted  
End Class  
```  
  
 <span data-ttu-id="7d43c-181"><xref:System.Xml.Serialization.XmlIncludeAttribute>를 사용할 때 <xref:System.Xml.Serialization.XmlSerializer> 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-181">You can use the <xref:System.Xml.Serialization.XmlIncludeAttribute> attribute when using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
 <span data-ttu-id="7d43c-182">특정 연산 또는 전체 서비스에 <xref:System.ServiceModel.ServiceKnownTypeAttribute> 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-182">You can apply the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute to an operation or to the entire service.</span></span> <span data-ttu-id="7d43c-183">호출할 메서드의 형식이나 이름을 사용하여 <xref:System.Runtime.Serialization.KnownTypeAttribute> 특성과 같은 알려진 형식 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-183">It accepts either a type or the name of the method to call to get a list of known types, just like the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span> <span data-ttu-id="7d43c-184">자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-184">For more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="specifying-the-use-and-style"></a><span data-ttu-id="7d43c-185">사용 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="7d43c-185">Specifying the Use and Style</span></span>  
 <span data-ttu-id="7d43c-186">WSDL(웹 서비스 기술 언어)을 사용하여 서비스를 설명하는 경우 문서 스타일과 RPC(원격 프로시저 호출) 스타일이 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-186">When describing services using Web Services Description Language (WSDL), the two commonly used styles are Document and remote procedure call (RPC).</span></span> <span data-ttu-id="7d43c-187">문서 스타일에서 전체 메시지 본문은 스키마를 사용하여 설명되고 WSDL은 해당 스키마 내의 요소를 참조하여 여러 메시지 본문 부분을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-187">In the Document style, the entire message body is described using the schema, and the WSDL describes the various message body parts by referring to elements within that schema.</span></span> <span data-ttu-id="7d43c-188">RPC 스타일에서 WSDL은 요소가 아닌 각 메시지 부분의 스키마 형식을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-188">In the RPC style, the WSDL refers to a schema type for each message part rather than an element.</span></span> <span data-ttu-id="7d43c-189">이 두 스타일 중 하나를 수동으로 선택해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-189">In some cases, you have to manually select one of these styles.</span></span> <span data-ttu-id="7d43c-190">둘 중 하나만 수동으로 설정하려면 <xref:System.ServiceModel.DataContractFormatAttribute>가 사용 중인 경우에는 `Style` 특성을 적용한 다음 <xref:System.Runtime.Serialization.DataContractSerializer> 속성을 설정하고, `Style`를 사용하는 경우에는 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 특성에 <xref:System.Xml.Serialization.XmlSerializer>을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-190">You can do this by applying the <xref:System.ServiceModel.DataContractFormatAttribute> attribute and setting the `Style` property (when the <xref:System.Runtime.Serialization.DataContractSerializer> is in use), or by setting `Style` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute (when using the <xref:System.Xml.Serialization.XmlSerializer>).</span></span>  
  
 <span data-ttu-id="7d43c-191">또한 <xref:System.Xml.Serialization.XmlSerializer>는 serialize된 두 가지 형식의 XML `Literal` 및 `Encoded`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-191">Additionally, the <xref:System.Xml.Serialization.XmlSerializer> supports two forms of serialized XML: `Literal` and `Encoded`.</span></span> <span data-ttu-id="7d43c-192">`Literal`은 가장 일반적으로 허용되는 폼이며 <xref:System.Runtime.Serialization.DataContractSerializer>에서 유일하게 지원하는 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-192">`Literal` is the most commonly accepted form, and is the only form the <xref:System.Runtime.Serialization.DataContractSerializer> supports.</span></span> <span data-ttu-id="7d43c-193">`Encoded`는 SOAP 사양의 5단원에 설명된 레거시 폼이며 새 서비스에는 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-193">`Encoded` is a legacy form described in section 5 of the SOAP specification, and is not recommended for new services.</span></span> <span data-ttu-id="7d43c-194">`Encoded` 모드로 전환하려면 `Use` 특성에서 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 속성을 `Encoded`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-194">To switch to `Encoded` mode, set the `Use` property on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to `Encoded`.</span></span>  
  
 <span data-ttu-id="7d43c-195">대부분의 경우 `Style` 및 `Use` 속성에 대한 기본 설정을 변경하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-195">In most cases, you should not change the default settings for the `Style` and `Use` properties.</span></span>  
  
## <a name="controlling-the-serialization-process"></a><span data-ttu-id="7d43c-196">Serialization 프로세스 제어</span><span class="sxs-lookup"><span data-stu-id="7d43c-196">Controlling the Serialization Process</span></span>  
 <span data-ttu-id="7d43c-197">여러 가지 방법으로 데이터를 serialize하는 방법을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-197">You can do a number of things to customize the way data is serialized.</span></span>  
  
### <a name="changing-server-serialization-settings"></a><span data-ttu-id="7d43c-198">서버 Serialization 설정 변경</span><span class="sxs-lookup"><span data-stu-id="7d43c-198">Changing Server Serialization Settings</span></span>  
 <span data-ttu-id="7d43c-199">기본 <xref:System.Runtime.Serialization.DataContractSerializer>가 사용 중인 경우 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 서비스에 적용하여 서비스에서 serialization 프로세스의 몇 가지 특성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-199">When the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, you can control some aspects of the serialization process on the service by applying the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the service.</span></span> <span data-ttu-id="7d43c-200">특히 `MaxItemsInObjectGraph` 속성을 사용하여 <xref:System.Runtime.Serialization.DataContractSerializer>가 deserialize하는 개체의 최대 개수를 제한하는 할당량을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-200">Specifically, you may use the `MaxItemsInObjectGraph` property to set the quota that limits the maximum number of objects the <xref:System.Runtime.Serialization.DataContractSerializer> deserializes.</span></span> <span data-ttu-id="7d43c-201">`IgnoreExtensionDataObject` 속성을 사용하여 라운드트립 버전 관리 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-201">You can use the `IgnoreExtensionDataObject` property to turn off the round-tripping versioning feature.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7d43c-202"> 할당량, 참조 [데이터에 대 한 보안 고려 사항](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-202"> quotas, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7d43c-203"> 라운드트립에, 참조 [이후 버전과 호환 데이터 계약](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-203"> round-tripping, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
```csharp  
[ServiceBehavior(MaxItemsInObjectGraph=100000)]  
public class MyDataService:IDataService  
{  
    public DataPoint[] GetData()  
    {  
       // Implementation omitted  
    }  
}  
```  
  
```vb  
<ServiceBehavior(MaxItemsInObjectGraph:=100000)>  
Public Class MyDataService Implements IDataService  
  
    Function GetData() As DataPoint()  
         ‘ Implementation omitted  
    End Function  
End Interface  
```  
  
### <a name="serialization-behaviors"></a><span data-ttu-id="7d43c-204">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="7d43c-204">Serialization Behaviors</span></span>  
 <span data-ttu-id="7d43c-205">serializer가 특정 작업에 사용되고 있는지 여부에 따라 자동으로 연결되는 두 가지 동작, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>를 <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-205">Two behaviors are available in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> and the <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> that are automatically plugged in depending on which serializer is in use for a particular operation.</span></span> <span data-ttu-id="7d43c-206">이러한 동작은 자동으로 적용되므로 일반적으로 사용자가 알아야 할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-206">Because these behaviors are applied automatically, you normally do not have to be aware of them.</span></span>  
  
 <span data-ttu-id="7d43c-207">그러나 `DataContractSerializerOperationBehavior`에는 serialization 프로세스를 사용자 지정하는 데 사용할 수 있는 `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject` 및 `DataContractSurrogate` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-207">However, the `DataContractSerializerOperationBehavior` has the `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject`, and `DataContractSurrogate` properties that you may use to customize the serialization process.</span></span> <span data-ttu-id="7d43c-208">처음 두 속성은 앞 단원에서 설명한 것과 의미가 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-208">The first two properties have the same meaning as discussed in the previous section.</span></span> <span data-ttu-id="7d43c-209">`DataContractSurrogate` 속성을 사용하여 serialization 프로세스를 사용자 지정하고 확장하는 데 필요한 강력한 메커니즘인 데이터 계약 서로게이트를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-209">You can use the `DataContractSurrogate` property to enable data contract surrogates, which are a powerful mechanism for customizing and extending the serialization process.</span></span> <span data-ttu-id="7d43c-210">자세한 내용은 참조 [데이터 계약 서로게이트](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-210">For more information, see [Data Contract Surrogates](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).</span></span>  
  
 <span data-ttu-id="7d43c-211">`DataContractSerializerOperationBehavior`를 사용하여 클라이언트와 서버 serialization 모두를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-211">You can use the `DataContractSerializerOperationBehavior` to customize both client and server serialization.</span></span> <span data-ttu-id="7d43c-212">다음 예제에서는 클라이언트에 `MaxItemsInObjectGraph` 할당량을 늘리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-212">The following example shows how to increase the `MaxItemsInObjectGraph` quota on the client.</span></span>  
  
```csharp  
ChannelFactory<IDataService> factory = new ChannelFactory<IDataService>(binding, address);  
foreach (OperationDescription op in factory.Endpoint.Contract.Operations)  
{  
    DataContractSerializerOperationBehavior dataContractBehavior =  
                op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
    if (dataContractBehavior != null)  
    {  
        dataContractBehavior.MaxItemsInObjectGraph = 100000;  
    }  
}  
IDataService client = factory.CreateChannel();  
```  
  
```vb  
Dim factory As ChannelFactory(Of IDataService) = New ChannelFactory(Of IDataService)(binding, address)  
For Each op As OperationDescription In factory.Endpoint.Contract.Operations  
        Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
        If dataContractBehavior IsNot Nothing Then  
            dataContractBehavior.MaxItemsInObjectGraph = 100000  
        End If  
     Next  
    Dim client As IDataService = factory.CreateChannel  
```  
  
 <span data-ttu-id="7d43c-213">다음은 자체 호스팅된 경우 서비스의 해당 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-213">Following is the equivalent code on the service, in the self-hosted case.</span></span>  
  
```csharp  
ServiceHost serviceHost = new ServiceHost(typeof(IDataService))  
foreach (ServiceEndpoint ep in serviceHost.Description.Endpoints)  
{  
foreach (OperationDescription op in ep.Contract.Operations)  
{  
        DataContractSerializerOperationBehavior dataContractBehavior =  
           op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
        if (dataContractBehavior != null)  
        {  
            dataContractBehavior.MaxItemsInObjectGraph = 100000;  
        }  
}  
}  
serviceHost.Open();  
```  
  
```vb  
Dim serviceHost As ServiceHost = New ServiceHost(GetType(IDataService))  
        For Each ep As ServiceEndpoint In serviceHost.Description.Endpoints  
            For Each op As OperationDescription In ep.Contract.Operations  
                Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
  
                If dataContractBehavior IsNot Nothing Then  
                    dataContractBehavior.MaxItemsInObjectGraph = 100000  
                End If  
            Next  
        Next  
        serviceHost.Open()  
```  
  
 <span data-ttu-id="7d43c-214">웹 호스팅의 경우 새 `ServiceHost` 파생 클래스를 만들고 서비스 호스트 팩터리를 사용하여 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-214">In the Web-hosted case, you must create a new `ServiceHost` derived class and use a service host factory to plug it in.</span></span>  
  
### <a name="controlling-serialization-settings-in-configuration"></a><span data-ttu-id="7d43c-215">구성에서 Serialization 설정 제어</span><span class="sxs-lookup"><span data-stu-id="7d43c-215">Controlling Serialization Settings in Configuration</span></span>  
 <span data-ttu-id="7d43c-216">`MaxItemsInObjectGraph` 및 `IgnoreExtensionDataObject`는 다음 예제에서처럼 `dataContractSerializer` 끝점 또는 서비스 동작을 사용하여 구성을 통해 제어될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-216">The `MaxItemsInObjectGraph` and `IgnoreExtensionDataObject` can be controlled through configuration by using the `dataContractSerializer` endpoint or service behavior, as shown in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="LargeQuotaBehavior">  
                    <dataContractSerializer  
                      maxItemsInObjectGraph="100000" />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <client>  
            <endpoint address=http://example.com/myservice  
                  behaviorConfiguration="LargeQuotaBehavior"  
                binding="basicHttpBinding" bindingConfiguration=""   
                            contract="IDataService"  
                name="" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a><span data-ttu-id="7d43c-217">공유 형식 Serialization, 개체 그래프 유지 및 사용자 지정 Serializer</span><span class="sxs-lookup"><span data-stu-id="7d43c-217">Shared Type Serialization, Object Graph Preservation, and Custom Serializers</span></span>  
 <span data-ttu-id="7d43c-218"><xref:System.Runtime.Serialization.DataContractSerializer>는 .NET 형식 이름이 아니라 데이터 계약 이름을 사용하여 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-218">The <xref:System.Runtime.Serialization.DataContractSerializer> serializes using data contract names and not .NET type names.</span></span> <span data-ttu-id="7d43c-219">이러한 serialization 방식은 서비스 기반 아키텍처 개념과 일치하며, 연결 계약에 영향을 주지 않고 .NET 형식을 변경할 수 있는 등 유연성을 높여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-219">This is consistent with service-oriented architecture tenets and allows for a great degree of flexibility—the .NET types can change without affecting the wire contract.</span></span> <span data-ttu-id="7d43c-220">드문 경우지만 실제 .NET 형식 이름을 serialize해야 하는 경우가 있으며, 이 경우 .NET Framework Remoting 기술과 유사한 클라이언트와 서버 간 밀접한 결합이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-220">In rare cases, you may want to serialize actual .NET type names, thereby introducing a tight coupling between the client and the server, similar to the .NET Framework remoting technology.</span></span> <span data-ttu-id="7d43c-221">일반적으로 .NET Framework Remoting에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 마이그레이션할 때 사용하는 드문 경우를 제외하고 이 방식은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-221">This is not a recommended practice, except in rare cases that usually occur when migrating to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] from .NET Framework remoting.</span></span> <span data-ttu-id="7d43c-222">이 경우에는 <xref:System.Runtime.Serialization.NetDataContractSerializer> 클래스 대신 <xref:System.Runtime.Serialization.DataContractSerializer> 클래스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-222">In this case, you must use the <xref:System.Runtime.Serialization.NetDataContractSerializer> class instead of the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 <span data-ttu-id="7d43c-223"><xref:System.Runtime.Serialization.DataContractSerializer>는 일반적으로 개체 그래프를 개체 트리로 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-223">The <xref:System.Runtime.Serialization.DataContractSerializer> normally serializes object graphs as object trees.</span></span> <span data-ttu-id="7d43c-224">즉, 같은 개체를 두 번 이상 참조하는 경우 두 번 이상 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-224">That is, if the same object is referred to more than once, it is serialized more than once.</span></span> <span data-ttu-id="7d43c-225">`PurchaseOrder`와 `billTo`라고 하는 두 가지 주소 형식 필드가 있는 `shipTo` 인스턴스를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-225">For example, consider a `PurchaseOrder` instance that has two fields of type Address called `billTo` and `shipTo`.</span></span> <span data-ttu-id="7d43c-226">두 필드가 같은 주소 인스턴스로 설정된 경우 serialization 및 deserialization 후 두 개의 동일한 주소 인스턴스가 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-226">If both fields are set to the same Address instance, there are two identical Address instances after serialization and deserialization.</span></span> <span data-ttu-id="7d43c-227"><xref:System.Xml.Serialization.XmlSerializer> 및 `Style`에 대해 앞 단원에서 설명한 대로 `Use`에서 사용할 수 있는 레거시 SOAP 인코딩 표준을 제외하고, XML로 개체 그래프를 나타낼 표준 상호 운용 가능한 방법이 없기 때문에 이와 같이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-227">This is done because there is no standard interoperable way to represent object graphs in XML (except for the legacy SOAP encoded standard available on the <xref:System.Xml.Serialization.XmlSerializer>, as described in the previous section on `Style` and `Use`).</span></span> <span data-ttu-id="7d43c-228">개체 그래프를 트리로 serialize하면 순환 참조가 있는 그래프를 serialize할 수 없는 등의 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-228">Serializing object graphs as trees has certain disadvantages, for example, graphs with circular references cannot be serialized.</span></span> <span data-ttu-id="7d43c-229">상호 운용이 가능하지 않아도 실제 개체 그래프 serialization으로 전환해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-229">Occasionally, it is necessary to switch to true object graph serialization, even though it is not interoperable.</span></span> <span data-ttu-id="7d43c-230">이 작업은 <xref:System.Runtime.Serialization.DataContractSerializer>로 설정된 `preserveObjectReferences` 매개 변수를 사용하여 생성된 `true`를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-230">This can be done by using the <xref:System.Runtime.Serialization.DataContractSerializer> constructed with the `preserveObjectReferences` parameter set to `true`.</span></span>  
  
 <span data-ttu-id="7d43c-231">기본 제공 serializer가 사용자 시나리오에 적합하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-231">Occasionally, the built-in serializers are not enough for your scenario.</span></span> <span data-ttu-id="7d43c-232">대부분의 경우 <xref:System.Runtime.Serialization.XmlObjectSerializer> 및 <xref:System.Runtime.Serialization.DataContractSerializer>가 모두 파생된 <xref:System.Runtime.Serialization.NetDataContractSerializer> 추상화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-232">In most cases, you can still use the <xref:System.Runtime.Serialization.XmlObjectSerializer> abstraction from which both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Runtime.Serialization.NetDataContractSerializer> derive.</span></span>  
  
 <span data-ttu-id="7d43c-233">앞의 세 가지 경우(.NET 형식 유지, 개체 그래프 유지 및 `XmlObjectSerializer` 기반의 완전한 사용자 지정 serialization) 모두 사용자 지정 serializer를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-233">The previous three cases (.NET type preservation, object graph preservation, and completely custom `XmlObjectSerializer`-based serialization) all require a custom serializer be plugged in.</span></span> <span data-ttu-id="7d43c-234">이렇게 하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-234">To do this, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="7d43c-235"><xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>에서 파생되는 고유한 동작을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-235">Write your own behavior deriving from the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.</span></span>  
  
2.  <span data-ttu-id="7d43c-236">두 개의 `CreateSerializer` 메서드를 재정의하여 고유한 serializer(<xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>가 `preserveObjectReferences`로 설정된 `true` 또는 사용자 지정 <xref:System.Runtime.Serialization.XmlObjectSerializer>)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-236">Override the two `CreateSerializer` methods to return your own serializer (either the <xref:System.Runtime.Serialization.NetDataContractSerializer>, the <xref:System.Runtime.Serialization.DataContractSerializer> with `preserveObjectReferences` set to `true`, or your own custom <xref:System.Runtime.Serialization.XmlObjectSerializer>).</span></span>  
  
3.  <span data-ttu-id="7d43c-237">서비스 호스트를 열거나 클라이언트 채널을 만들기 전에 기존 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> 동작을 제거하고 이전 단계에서 만든 사용자 지정 파생 클래스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-237">Before opening the service host or creating a client channel, remove the existing <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> behavior and plug in the custom derived class that you created in the previous steps.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7d43c-238"> 고급 serialization 개념, 참조 [Serialization 및 Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d43c-238"> advanced serialization concepts, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d43c-239">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d43c-239">See Also</span></span>  
 [<span data-ttu-id="7d43c-240">XmlSerializer 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="7d43c-240">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 [<span data-ttu-id="7d43c-241">방법: 스트리밍 사용</span><span class="sxs-lookup"><span data-stu-id="7d43c-241">How to: Enable Streaming</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)  
 [<span data-ttu-id="7d43c-242">방법: 클래스 또는 구조체에 대한 기본 데이터 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="7d43c-242">How to: Create a Basic Data Contract for a Class or Structure</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
