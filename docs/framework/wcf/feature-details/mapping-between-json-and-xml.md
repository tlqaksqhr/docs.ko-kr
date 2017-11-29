---
title: "JSON과 XML 간의 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8bcc8f178f76c536b189058210a586d0d37a1834
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-between-json-and-xml"></a><span data-ttu-id="37668-102">JSON과 XML 간의 매핑</span><span class="sxs-lookup"><span data-stu-id="37668-102">Mapping Between JSON and XML</span></span>
<span data-ttu-id="37668-103"><xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>에서 생성된 판독기 및 작성기는 JSON(JavaScript Object Notation) 콘텐츠를 통해 XML API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-103">The readers and writers produced by the <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> provide an XML API over JavaScript Object Notation (JSON) content.</span></span> <span data-ttu-id="37668-104">JSON은 JavaScript 개체 리터럴의 하위 집합을 사용하여 데이터를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-104">JSON encodes data using a subset of the object literals of JavaScript.</span></span> <span data-ttu-id="37668-105">이 팩터리에서 생성된 판독기와 작성기는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 또는 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>을 사용하여 <xref:System.ServiceModel.WebHttpBinding> 응용 프로그램에서 JSON 콘텐츠를 보내고 받을 때도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-105">The readers and writers produced by this factory are also used when JSON content is being sent or received by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications using the <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> or the <xref:System.ServiceModel.WebHttpBinding>.</span></span>  
  
 <span data-ttu-id="37668-106">JSON 판독기는 JSON 콘텐츠를 사용하여 초기화될 때 텍스트 XML 판독기가 XML의 인스턴스에 대해 수행하는 방식과 같은 방식으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-106">When initialized with JSON content, the JSON reader behaves in the same way that a textual XML reader does over an instance of XML.</span></span> <span data-ttu-id="37668-107">JSON 작성기는 텍스트 XML 판독기에서 특정 XML 인스턴스를 생성하는 호출 시퀀스가 제공될 때 JSON 콘텐츠를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-107">The JSON writer, when given a sequence of calls that on a textual XML reader produces a certain XML instance, writes out JSON content.</span></span> <span data-ttu-id="37668-108">고급 시나리오에서 사용할 XML의 이 인스턴스와 JSON 콘텐츠 간 매핑은 이 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-108">The mapping between this instance of XML and the JSON content is described in this topic for use in advanced scenarios.</span></span>  
  
 <span data-ttu-id="37668-109">내부적으로 JSON은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 처리되면 XML infoset으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-109">Internally, JSON is represented as an XML infoset when processed by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="37668-110">일반적으로 매핑은 논리적인 표현일 뿐이므로 이러한 내부 표현에 관여할 필요가 없습니다. JSON은 실제로 메모리의 XML로 변환되거나 XML에서 JSON으로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-110">Normally you do not have to be concerned with this internal representation as the mapping is only a logical one: JSON is normally not physically converted to XML in memory or converted to JSON from XML.</span></span> <span data-ttu-id="37668-111">매핑이란 XML API를 사용하여 JSON 콘텐츠에 액세스하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-111">The mapping means that XML APIs are used to access JSON content.</span></span>  
  
 <span data-ttu-id="37668-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 JSON을 사용하는 경우 일반적인 시나리오는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>가 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> 동작이나 <xref:System.ServiceModel.Description.WebHttpBehavior> 동작에 의해 적절히 자동으로 연결되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-112">When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses JSON, the usual scenario is that the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is automatically plugged in by the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior, or by the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior when appropriate.</span></span> <span data-ttu-id="37668-113"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 JSON과 XML infoset 간 매핑을 이해하고 직접 JSON을 처리하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-113">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> understands the mapping between JSON and the XML infoset and acts as if it is dealing with JSON directly.</span></span> <span data-ttu-id="37668-114">XML이 다음 매핑을 따른다는 이해를 바탕으로 XML 판독기나 작성기에 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-114">(It is possible to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> with any XML reader or writer, with the understanding that the XML conforms to the following mapping.)</span></span>  
  
 <span data-ttu-id="37668-115">고급 시나리오에서 다음 매핑에 직접 액세스해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-115">In advanced scenarios, it may become necessary to directly access the following mapping.</span></span> <span data-ttu-id="37668-116">이러한 경우는 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용하지 않고 사용자 지정 방식으로 JSON을 serialize 및 deserialize하거나 JSON이 포함된 메시지의 <xref:System.ServiceModel.Channels.Message> 형식을 직접 처리할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-116">These scenarios occur when you want to serialize and deserialize JSON in custom ways, without relying on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, or when dealing with the <xref:System.ServiceModel.Channels.Message> type directly for messages containing JSON.</span></span> <span data-ttu-id="37668-117">JSON-XML 매핑은 메시지 로깅에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-117">The JSON-XML mapping is also used for message logging.</span></span> <span data-ttu-id="37668-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 메시지 로깅 기능을 사용할 때 JSON 메시지는 다음 단원에 설명된 매핑에 따라 XML로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-118">When using the message logging feature in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], JSON messages is logged as XML according to the mapping described in the next section.</span></span>  
  
 <span data-ttu-id="37668-119">매핑에 대한 개념을 명확히 하기 위해 다음 예제가 JSON 문서에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-119">To clarify the concept of a mapping, the following example is of a JSON document.</span></span>  
  
```json  
{"product":"pencil","price":12}  
```  
  
 <span data-ttu-id="37668-120">앞에서 언급한 판독기 중 하나를 사용하여 이 JSON 문서를 읽으려면 다음 XML 문서를 읽을 때와 동일한 <xref:System.Xml.XmlDictionaryReader> 호출 시퀀스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-120">To read this JSON document using one of the readers previously mentioned, use the same sequence of <xref:System.Xml.XmlDictionaryReader> calls as you would to read the following XML document.</span></span>  
  
```xml  
<root type="object">  
    <product type="string">pencil</product>  
    <price type="number">12</price>  
</root>  
```  
  
 <span data-ttu-id="37668-121">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 예제의 JSON 메시지를 받고 기록한 경우에는 앞의 로그에서 XML 조각을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-121">Furthermore, if the JSON message in the example is received by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and logged, you would see the XML fragment in the preceding log.</span></span>  
  
## <a name="mapping-between-json-and-the-xml-infoset"></a><span data-ttu-id="37668-122">JSON과 XML Infoset 간의 매핑</span><span class="sxs-lookup"><span data-stu-id="37668-122">Mapping Between JSON and the XML Infoset</span></span>  
 <span data-ttu-id="37668-123">공식적으로, 간에 매핑이 일어납니다 JSON에 설명 된 대로 [RFC 4627](http://go.microsoft.com/fwlink/?LinkId=98808) (있는 경우 제외 특정 제한 사항을 완화 하 고 특정 추가 기타 제한 사항) 및 XML infoset (및 하지 텍스트 XML)으로 설명 된 [XML 정보 설정](http://go.microsoft.com/fwlink/?LinkId=98809) 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-123">Formally, the mapping is between JSON as described in [RFC 4627](http://go.microsoft.com/fwlink/?LinkId=98808) (except with certain restrictions relaxed and certain other restrictions added) and the XML infoset (and not textual XML) as described in [XML Information Set](http://go.microsoft.com/fwlink/?LinkId=98809) .</span></span> <span data-ttu-id="37668-124">이 항목의 정의 대 한 참조 *정보 항목* 및 [대괄호] 안에 있는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-124">See this topic for the definitions of *information items* and fields in [square brackets].</span></span>  
  
 <span data-ttu-id="37668-125">빈 JSON 문서는 빈 XML 문서에 매핑되고 빈 XML 문서는 빈 JSON 문서에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-125">A blank JSON document maps to blank XML document, and a blank XML document maps to a blank JSON document.</span></span> <span data-ttu-id="37668-126">XML과 JSON 간 매핑에서 문서 뒤에 선행 공백과 후행 공백을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-126">On the XML to JSON mapping, preceding whitespace and trailing whitespace after the document are not allowed.</span></span>  
  
 <span data-ttu-id="37668-127">매핑은 DII(문서 정보 항목) 또는 EII(요소 정보 항목)와 JSON 사이에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-127">The mapping is defined between either a Document Information Item (DII) or an Element Information Item (EII) and JSON.</span></span> <span data-ttu-id="37668-128">EII 또는 DII의 [document element] 속성을 루트 JSON 요소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-128">The EII, or the DII’s [document element] property, is referred to as the Root JSON Element.</span></span> <span data-ttu-id="37668-129">문서 조각(여러 루트 요소가 있는 XML)은 이 매핑에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-129">Note that document fragments (XML with multiple root elements) are not supported in this mapping.</span></span>  
  
 <span data-ttu-id="37668-130">예제: 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37668-130">Example: The following document:</span></span>  
  
 `<?xml version="1.0"?>`  
  
 `<root type="number">42</root>`  
  
 <span data-ttu-id="37668-131">다음 요소를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37668-131">And the following element:</span></span>  
  
 `<root type="number">42</root>`  
  
 <span data-ttu-id="37668-132">모두 JSON에 대한 매핑이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-132">Both have a mapping to JSON.</span></span> <span data-ttu-id="37668-133"><`root`> 요소는 두 경우 모두 루트 JSON 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-133">The <`root`> element is the Root JSON Element in both cases.</span></span>  
  
 <span data-ttu-id="37668-134">또한 DII의 경우 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-134">Furthermore, in the case of a DII, the following should be considered:</span></span>  
  
-   <span data-ttu-id="37668-135">[children] 목록의 일부 항목이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-135">Some items in the [children] list must not be present.</span></span> <span data-ttu-id="37668-136">JSON에서 매핑된 XML을 읽을 때는 이 사실에 의존하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="37668-136">Do not rely on this fact when reading XML mapped from JSON.</span></span>  
  
-   <span data-ttu-id="37668-137">[children] 목록에는 주석 정보 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-137">The [children] list holds no comment information items.</span></span>  
  
-   <span data-ttu-id="37668-138">[children] 목록에는 DTD 정보 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-138">The [children] list holds no DTD information items.</span></span>  
  
-   <span data-ttu-id="37668-139">[Children] 목록 없는 개인 정보 (PI) 정보 항목을 보유 한 (의 \<? xml … > 선언은 PI 정보 항목으로 간주 되지 않으므로)</span><span class="sxs-lookup"><span data-stu-id="37668-139">The [children] list holds no personal Information (PI) information items (the \<?xml…> declaration is not considered a PI information item)</span></span>  
  
-   <span data-ttu-id="37668-140">[notations] 집합이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-140">The [notations] set is empty.</span></span>  
  
-   <span data-ttu-id="37668-141">[unparsed entities] 집합이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-141">The [unparsed entities] set is empty.</span></span>  
  
 <span data-ttu-id="37668-142">예제: [children]에 PI 및 주석이 있기 때문에 다음 문서에는 JSON에 대한 매핑이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-142">Example: The following document has no mapping to JSON because [children] holds a PI and a comment.</span></span>  
  
 `<?xml version="1.0"?>`  
  
 `<!--comment--><?pi?>`  
  
 `<root type="number">42</root>`  
  
 <span data-ttu-id="37668-143">루트 JSON 요소에 대한 EII에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-143">The EII for the Root JSON Element has the following characteristics:</span></span>  
  
-   <span data-ttu-id="37668-144">[local name]에는 값 "root"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-144">[local name] has the value "root".</span></span>  
  
-   <span data-ttu-id="37668-145">[namespace name]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-145">[namespace name] has no value.</span></span>  
  
-   <span data-ttu-id="37668-146">[prefix]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-146">[prefix] has no value.</span></span>  
  
-   <span data-ttu-id="37668-147">[children]에는 나중에 설명될 내부 요소를 나타내는 EII나 나중에 설명될 문자 정보 항목을 나타내는 CII 중 하나만 포함되거나 이 두 가지 모두 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-147">[children] may either contain EIIs (which represent Inner Elements as described further) or CIIs (Character Information Items as described further) or none of these, but not both.</span></span>  
  
-   <span data-ttu-id="37668-148">[attributes]에는 다음과 같은 선택적 AII(특성 정보 항목)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-148">[attributes] may contain the following optional attribute information items (AIIs)</span></span>  
  
-   <span data-ttu-id="37668-149">아래에 설명된 JSON 형식 특성("type").</span><span class="sxs-lookup"><span data-stu-id="37668-149">The JSON Type Attribute ("type") as described further.</span></span> <span data-ttu-id="37668-150">이 특성은 매핑된 XML에서 JSON 형식(문자열, 숫자, 부울, 개체, 배열 또는 null)을 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-150">This attribute is used to preserve the JSON type (string, number, boolean, object, array or null) in the mapped XML.</span></span>  
  
-   <span data-ttu-id="37668-151">아래에 설명된 데이터 계약 이름 특성("__type").</span><span class="sxs-lookup"><span data-stu-id="37668-151">The Data Contract Name Attribute ("__type") as described further.</span></span> <span data-ttu-id="37668-152">이 특성은 JSON 형식 특성도 있고 해당 [normalized value]가 "object"인 경우에만 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-152">This attribute is can only be present if the JSON type attribute is also present and its [normalized value] is "object".</span></span> <span data-ttu-id="37668-153">이 특성은 파생 형식이 serialize되고 기본 형식이 필요한 다형 사례처럼 `DataContractJsonSerializer`에서 데이터 계약 형식 정보를 유지하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-153">This attribute is used by the `DataContractJsonSerializer` to preserve data contract type information - for example, in polymorphic cases where a derived type is serialized and where a base type is expected.</span></span> <span data-ttu-id="37668-154">`DataContractJsonSerializer`로 작업하지 않는 경우 대부분 이 특성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-154">If you are not working with the `DataContractJsonSerializer`, in most cases, this attribute is ignored.</span></span>  
  
-   <span data-ttu-id="37668-155">[in-scope namespaces]에는 infoset 사양에 지정된 대로 "http://www.w3.org/XML/1998/namespace"에 대한 "xml" 바인딩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-155">[in-scope namespaces] contains the binding of "xml" to "http://www.w3.org/XML/1998/namespace" as mandated by the infoset specification.</span></span>  
  
-   <span data-ttu-id="37668-156">[children], [attributes] 및 [in-scope namespaces]에는 앞에서 지정한 것 이외의 항목이 없어야 하고, [namespace attributes]에는 멤버가 없어야 하지만 JSON에서 매핑된 XML을 읽을 때는 이러한 사항을 고려하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="37668-156">[children], [attributes] and [in-scope namespaces] must not have any items other than as specified previously and [namespace attributes] must have no members, but do not rely on these facts when reading XML mapped from JSON.</span></span>  
  
 <span data-ttu-id="37668-157">예제: [namespace attributes]가 비어 있지 않기 때문에 다음 문서에는 JSON에 대한 매핑이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-157">Example: The following document has no mapping to JSON because [namespace attributes] is not empty.</span></span>  
  
 `<?xml version="1.0"?>`  
  
 `<root  xmlns:a="myattributevalue">42</root>`  
  
 <span data-ttu-id="37668-158">JSON 형식 특성에 대한 AII에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-158">The AII for the JSON Type Attribute has the following characteristics:</span></span>  
  
-   <span data-ttu-id="37668-159">[namespace name]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-159">[namespace name] has no value.</span></span>  
  
-   <span data-ttu-id="37668-160">[prefix]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-160">[prefix] has no value.</span></span>  
  
-   <span data-ttu-id="37668-161">[local name]은 "type"입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-161">[local name] is "type".</span></span>  
  
-   <span data-ttu-id="37668-162">[normalized value]는 다음 단원에서 설명하는 사용 가능한 형식 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-162">[normalized value] is one of the possible type values described in the following section.</span></span>  
  
-   <span data-ttu-id="37668-163">[specified]는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-163">[specified] is `true`.</span></span>  
  
-   <span data-ttu-id="37668-164">[attribute type]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-164">[attribute type] has no value.</span></span>  
  
-   <span data-ttu-id="37668-165">[references]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-165">[references] has no value.</span></span>  
  
 <span data-ttu-id="37668-166">데이터 계약 이름 특성에 대한 AII에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-166">The AII for the Data Contract Name Attribute has the following characteristics:</span></span>  
  
-   <span data-ttu-id="37668-167">[namespace name]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-167">[namespace name] has no value.</span></span>  
  
-   <span data-ttu-id="37668-168">[prefix]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-168">[prefix] has no value.</span></span>  
  
-   <span data-ttu-id="37668-169">[local name]은 "__type"(두 개의 밑줄과 "type")입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-169">[local name] is "__type" (two underscores and then "type").</span></span>  
  
-   <span data-ttu-id="37668-170">[normalized value]는 올바른 유니코드 문자열입니다. JSON에 대한 이 문자열의 매핑은 다음 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-170">[normalized value] is any valid Unicode string – the mapping of this string to JSON is described in the following section.</span></span>  
  
-   <span data-ttu-id="37668-171">[specified]는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-171">[specified] is `true`.</span></span>  
  
-   <span data-ttu-id="37668-172">[attribute type]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-172">[attribute type] has no value.</span></span>  
  
-   <span data-ttu-id="37668-173">[references]에는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-173">[references] has no value.</span></span>  
  
 <span data-ttu-id="37668-174">루트 JSON 요소 내에 포함된 내부 요소 또는 기타 내부 요소에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-174">Inner elements contained within the Root JSON Element or other inner elements have the following characteristics:</span></span>  
  
-   <span data-ttu-id="37668-175">[local name]에는 설명한 대로 아무 값이나 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-175">[local name] may have any value as described further</span></span>  
  
-   <span data-ttu-id="37668-176">[namespace name], [prefix], [children], [attributes], [namespace attributes] 및 [in-scope namespaces]는 루트 JSON 요소와 동일한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="37668-176">[namespace name], [prefix], [children], [attributes], [namespace attributes], and [in-scope namespaces] are subject to the same rules as the Root JSON Element.</span></span>  
  
 <span data-ttu-id="37668-177">루트 JSON 요소와 내부 요소에서 JSON 형식 특성은 JSON에 대한 매핑 및 가능한 [children]과 [children]의 해석을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-177">In both the Root JSON Element and the inner elements, the JSON Type Attribute defines the mapping to JSON and the possible [children] and their interpretation.</span></span> <span data-ttu-id="37668-178">특성의 [normalized value]는 대/소문자를 구분하므로 소문자여야 하고 공백을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-178">The attribute’s [normalized value] is case-sensitive and must be lowercase, and cannot contain whitespace.</span></span>  
  
|<span data-ttu-id="37668-179">`JSON Type Attribute` AII의 [normalized value]</span><span class="sxs-lookup"><span data-stu-id="37668-179">[normalized value] of `JSON Type Attribute`’s AII</span></span>|<span data-ttu-id="37668-180">허용되는 해당 EII의 [children]</span><span class="sxs-lookup"><span data-stu-id="37668-180">Allowed [children] of the corresponding EII</span></span>|<span data-ttu-id="37668-181">JSON에 매핑</span><span class="sxs-lookup"><span data-stu-id="37668-181">Mapping to JSON</span></span>|  
|---------------------------------------------------------|---------------------------------------------------|---------------------|  
|<span data-ttu-id="37668-182">`string`(또는 JSON 형식 AII 없음)</span><span class="sxs-lookup"><span data-stu-id="37668-182">`string` (or absence of the JSON type AII)</span></span><br /><br /> <span data-ttu-id="37668-183">`string`이거나 JSON 형식 AII이 없으면 똑같이 `string`이 기본값으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-183">A `string` and the absence of the JSON type AII are the same makes `string` the default.</span></span><br /><br /> <span data-ttu-id="37668-184">따라서 `<root> string1</root>`는 JSON `string` "string1"에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-184">So, `<root> string1</root>` maps to the JSON `string` "string1".</span></span>|<span data-ttu-id="37668-185">0 이나 더 많은 Cii</span><span class="sxs-lookup"><span data-stu-id="37668-185">0 or more CIIs</span></span>|<span data-ttu-id="37668-186">JSON `string`(JSON RFC, 섹션 2.5).</span><span class="sxs-lookup"><span data-stu-id="37668-186">A JSON `string` (JSON RFC, section 2.5).</span></span> <span data-ttu-id="37668-187">각 `char`은 CII의 [character code]에 해당하는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-187">Each `char` is a character that corresponds to the [character code] from the CII.</span></span> <span data-ttu-id="37668-188">CII가 없을 경우에는 빈 JSON `string`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-188">If there are no CIIs, it maps to an empty JSON `string`.</span></span><br /><br /> <span data-ttu-id="37668-189">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-189">Example: The following element maps to a JSON fragment:</span></span><br /><br /> `<root type="string">42</root>`<br /><br /> <span data-ttu-id="37668-190">JSON 조각은 "42"입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-190">The JSON fragment is "42".</span></span><br /><br /> <span data-ttu-id="37668-191">XML과 JSON 간 매핑에서 이스케이프해야 하는 문자는 이스케이프된 문자에 매핑되고 그 외 다른 모든 문자는 이스케이프되지 않은 문자에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-191">On XML to JSON mapping, characters that must be escaped map to escaped characters, all others map to characters that are not escaped.</span></span> <span data-ttu-id="37668-192">"/" 문자는 특별 한 – 수 없는 경우에 이스케이프 됩니다 (로 작성 "\\/").</span><span class="sxs-lookup"><span data-stu-id="37668-192">The "/" character is special – it is escaped even though it does not have to be (written out as "\\/").</span></span><br /><br /> <span data-ttu-id="37668-193">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-193">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> <span data-ttu-id="37668-194">JSON 조각은 "는 \\" da\\/ta\\""입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-194">The JSON fragment is "the \\"da\\/ta\\"".</span></span><br /><br /> <span data-ttu-id="37668-195">JSON과 XML 간 매핑에서 이스케이프된 문자와 이스케이프되지 않은 문자는 해당 [character code]에 올바르게 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-195">On JSON to XML mapping, any escaped characters and characters that are not escaped map correctly to the corresponding [character code].</span></span><br /><br /> <span data-ttu-id="37668-196">예제: JSON 조각 "\u0041BC"는 다음 XML 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-196">Example: The JSON fragment "\u0041BC", maps to the following XML element.</span></span><br /><br /> `<root type="string">ABC</root>`<br /><br /> <span data-ttu-id="37668-197">문자열은 XML에 매핑되지 않는 공백(JSON RFC의 섹션 2에 있는 'ws')으로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-197">The string can be surrounded by whitespace ('ws' in section 2 of the JSON RFC) that does not get mapped to XML.</span></span><br /><br /> <span data-ttu-id="37668-198">예제: JSON 조각           "ABC"(첫 번째 큰따옴표 앞에 공백이 있음)는 다음 XML 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-198">Example: The JSON fragment           "ABC", (there are spaces before the first double quote), maps to the following XML element.</span></span><br /><br /> `<root type="string">ABC</root>`<br /><br /> <span data-ttu-id="37668-199">XML의 공백은 JSON의 공백에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-199">Any whitespace in XML maps to whitespace in JSON.</span></span><br /><br /> <span data-ttu-id="37668-200">예제: 다음 XML 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-200">Example: The following XML element maps to a JSON fragment.</span></span><br /><br /> `<root type="string">  A BC      </root>`<br /><br /> <span data-ttu-id="37668-201">JSON 조각은 " A BC "입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-201">The JSON fragment is " A BC ".</span></span>|  
|`number`|<span data-ttu-id="37668-202">1개 이상의 CII</span><span class="sxs-lookup"><span data-stu-id="37668-202">1 or more CIIs</span></span>|<span data-ttu-id="37668-203">JSON `number`(JSON RFC, 섹션 2.4)는 공백으로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-203">A JSON `number` (JSON RFC, section 2.4), possibly surrounded by whitespace.</span></span> <span data-ttu-id="37668-204">숫자/공백 조합의 각 문자는 CII에서 [character code]에 해당하는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-204">Each character in the number/whitespace combination is a character that corresponds to the [character code] from the CII.</span></span><br /><br /> <span data-ttu-id="37668-205">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-205">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="number">    42</root>`<br /><br /> <span data-ttu-id="37668-206">JSON 조각은    42입니다</span><span class="sxs-lookup"><span data-stu-id="37668-206">The JSON fragment is    42</span></span><br /><br /> <span data-ttu-id="37668-207">(공백은 유지됨).</span><span class="sxs-lookup"><span data-stu-id="37668-207">(Whitespace is preserved).</span></span>|  
|`boolean`|<span data-ttu-id="37668-208">4개나 5개의 CII(`true` 또는 `false`에 해당)는 추가 공백 CII로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-208">4 or 5 CIIs (which corresponds to `true` or `false`), possibly surrounded by additional whitespace CIIs.</span></span>|<span data-ttu-id="37668-209">문자열 "true"에 해당하는 CII 시퀀스는 리터럴 `true`에 매핑되고 문자열 "false"에 해당하는 CII 시퀀스는 리터럴 `false`에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-209">A CII sequence that corresponds to the string "true" is mapped to the literal `true`, and a CII sequence that corresponds to the string "false" is mapped to the literal `false`.</span></span> <span data-ttu-id="37668-210">주변의 공백은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-210">Surrounding whitespace is preserved.</span></span><br /><br /> <span data-ttu-id="37668-211">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-211">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="boolean"> false</root>`<br /><br /> <span data-ttu-id="37668-212">JSON 조각은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-212">The JSON fragment is `false`.</span></span>|  
|`null`|<span data-ttu-id="37668-213">아무 것도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-213">None allowed.</span></span>|<span data-ttu-id="37668-214">리터럴 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-214">The literal `null`.</span></span> <span data-ttu-id="37668-215">JSON과 XML 간 매핑에서 `null`은 XML에 매핑되지 않는 공백(섹션 2에 있는 ‘ws’)으로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-215">On JSON to XML mapping, the `null` may be surrounded by whitespace (‘ws’ in section 2) that does not get mapped to XML.</span></span><br /><br /> <span data-ttu-id="37668-216">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-216">Example: The following element maps to a JSON fragment.</span></span><br /><br /> `<root type="null"/>`<br /><br /> <span data-ttu-id="37668-217">또는</span><span class="sxs-lookup"><span data-stu-id="37668-217">or</span></span><br /><br /> `<root type="null"></root>`<br /><br /> <span data-ttu-id="37668-218">:</span><span class="sxs-lookup"><span data-stu-id="37668-218">:</span></span><br /><br /> <span data-ttu-id="37668-219">두 경우 모두 JSON 조각은 `Null`입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-219">The JSON fragment in both cases is `Null`.</span></span>|  
|`object`|<span data-ttu-id="37668-220">0개 이상의 EII.</span><span class="sxs-lookup"><span data-stu-id="37668-220">0 or more EIIs.</span></span>|<span data-ttu-id="37668-221">JSON RFC 섹션 2.2의 `begin-object`(왼쪽 중괄호)입니다. 이 값 다음에는 아래에서 설명하는 것처럼 각 EII에 대한 멤버 레코드가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37668-221">A `begin-object` (left curly brace) as in section 2.2 of the JSON RFC, followed by a member record for each EII as described further.</span></span> <span data-ttu-id="37668-222">EII가 두 개 이상 있을 경우 멤버 레코드 사이에 값 구분 기호(쉼표)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-222">If there is more than one EII, there are value-separators (commas) between the member records.</span></span> <span data-ttu-id="37668-223">그 다음에 끝 개체(오른쪽 중괄호)가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37668-223">All this is followed by an end-object (right curly brace).</span></span><br /><br /> <span data-ttu-id="37668-224">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-224">Example: The following element maps to the JSON fragment.</span></span><br /><br /> <span data-ttu-id="37668-225">\<루트 형식 = "object" ></span><span class="sxs-lookup"><span data-stu-id="37668-225">\<root type="object"></span></span><br /><br /> <span data-ttu-id="37668-226">\<type1 형식 = "string" > aaa\</type1 ></span><span class="sxs-lookup"><span data-stu-id="37668-226">\<type1 type="string">aaa\</type1></span></span><br /><br /> <span data-ttu-id="37668-227">\<유형 2 형식 = "string" > bbb\</type2 ></span><span class="sxs-lookup"><span data-stu-id="37668-227">\<type2 type="string">bbb\</type2></span></span><br /><br /> <span data-ttu-id="37668-228">\<루트/></span><span class="sxs-lookup"><span data-stu-id="37668-228">\</root ></span></span><br /><br /> <span data-ttu-id="37668-229">JSON 조각은 {"type1":"aaa","type2":"bbb"}입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-229">The JSON fragment is {"type1":"aaa","type2":"bbb"}.</span></span><br /><br /> <span data-ttu-id="37668-230">데이터 계약 형식 특성이 XML과 JSON 간 매핑에 표시되면 추가 멤버 레코드가 처음에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-230">If the Data Contract Type Attribute is present on XML to JSON mapping, then an additional Member Record is inserted at the beginning.</span></span> <span data-ttu-id="37668-231">해당 이름은 데이터 계약 형식 특성("__type")의 [local name]이고 값은 특성의 [normalized value]입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-231">Its name is the [local name] of the Data Contract Type Attribute ("__type"), and its value is the attribute's [normalized value].</span></span> <span data-ttu-id="37668-232">반대로 JSON과 XML 간 매핑에서, 첫 번째 멤버 레코드의 이름이 데이터 계약 형식 특성 [로컬 name]에 (즉, "\_입력 (_t)"), 해당 데이터 계약 형식 특성이 매핑된 XML에 있으면 해당 EII 않습니다 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-232">Conversely, on JSON to XML mapping, if the first member-record’s name is the [local name] of the Data Contract Type Attribute (that is, "\__type"), a corresponding Data Contract Type Attribute is present in the mapped XML, but a corresponding EII is not present.</span></span> <span data-ttu-id="37668-233">이 멤버 레코드는 이러한 특수한 매핑이 적용되는 JSON 개체에서 먼저 발생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-233">Note that this member record must occur first in the JSON object for this special mapping to apply.</span></span> <span data-ttu-id="37668-234">이는 멤버 레코드의 순서가 중요하지 않은 일반 JSON 처리에서 출발 지점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37668-234">This represents a departure from usual JSON processing, where the order of member records is not significant.</span></span><br /><br /> <span data-ttu-id="37668-235">예제:</span><span class="sxs-lookup"><span data-stu-id="37668-235">Example:</span></span><br /><br /> <span data-ttu-id="37668-236">다음 JSON 조각은 XML에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-236">The following JSON fragment maps to XML.</span></span><br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> <span data-ttu-id="37668-237">다음 코드는 XML입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-237">The XML is the following code.</span></span><br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> <span data-ttu-id="37668-238">에 \_입력 (_t) AII이 있지만 없는 \_입력 EII (_t).</span><span class="sxs-lookup"><span data-stu-id="37668-238">Notice that the \__type AII is present, but there is no \__type EII.</span></span><br /><br /> <span data-ttu-id="37668-239">그러나 다음 예제에서처럼 JSON에서 순서는 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-239">However, if the order in the JSON is reversed as shown in the following example.</span></span><br /><br /> <span data-ttu-id="37668-240">{"name": "John","\_입력 (_t)": "Person"을 (를)</span><span class="sxs-lookup"><span data-stu-id="37668-240">{"name":"John","\__type":"Person"}</span></span><br /><br /> <span data-ttu-id="37668-241">해당 XML이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-241">The corresponding XML is shown.</span></span><br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> <span data-ttu-id="37668-242">즉, \_입력 (_t) 사라지게 있고 특별 한 의미 EII에 매핑됩니다 평소와 같이 AII가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-242">That is, \__type ceases to have special meaning and maps to an EII as usual, not AII.</span></span><br /><br /> <span data-ttu-id="37668-243">JSON 값에 매핑될 때 AII의 [normalized value]에 대한 이스케이프/이스케이프 취소 규칙은 이 테이블의 "string" 행에 지정된 JSON 문자열에 대한 규칙과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-243">Escaping/unescaping rules for the AII’s [normalized value] when mapped to a JSON value are the same as for JSON strings, specified in the "string" row of this table.</span></span><br /><br /> <span data-ttu-id="37668-244">예제:</span><span class="sxs-lookup"><span data-stu-id="37668-244">Example:</span></span><br /><br /> `<root type="object" __type="\abc" />`<br /><br /> <span data-ttu-id="37668-245">앞의 예제가 다음 JSON에 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-245">to the previous example can be mapped to the following JSON.</span></span><br /><br /> `{"__type":"\\abc"}`<br /><br /> <span data-ttu-id="37668-246">xml과 JSON 간 매핑에서 첫 번째 EII의 [로컬 이름] 수 없습니다 "\_입력 (_t)"입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-246">On an XML to JSON mapping, the first EII’s [local name] must not be "\__type".</span></span><br /><br /> <span data-ttu-id="37668-247">공백(`ws`)은 개체에 대한 XML과 JSON 간 매핑에서 생성되지 않고 JSON과 XML 간 매핑에서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-247">Whitespace (`ws`) is never generated on XML to JSON mapping for objects and is ignored on JSON to XML mapping.</span></span><br /><br /> <span data-ttu-id="37668-248">예제: 다음 JSON 조각은 XML 요소에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-248">Example: The following JSON fragment maps to an XML element.</span></span><br /><br /> <span data-ttu-id="37668-249">{   "ccc"   :  "aaa",   "ddd"    :"bbb"}</span><span class="sxs-lookup"><span data-stu-id="37668-249">{   "ccc"   :  "aaa",   "ddd"    :"bbb"}</span></span><br /><br /> <span data-ttu-id="37668-250">다음 코드에서는 XML 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37668-250">The XML element is shown in the following code.</span></span><br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|  
<span data-ttu-id="37668-251">광선 '</span><span class="sxs-lookup"><span data-stu-id="37668-251">ray\`</span></span>|<span data-ttu-id="37668-252">0개 이상의 EII</span><span class="sxs-lookup"><span data-stu-id="37668-252">0 or more EIIs</span></span>|<span data-ttu-id="37668-253">JSON RFC 섹션 2.3의 시작 배열(왼쪽 대괄호)입니다. 이 값 다음에는 아래에서 설명하는 것처럼 각 EII에 대한 배열 레코드가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37668-253">A begin-array (left square bracket) as in section 2.3 of the JSON RFC, followed by an array record for each EII as described further.</span></span> <span data-ttu-id="37668-254">EII가 두 개 이상 있을 경우 배열 레코드 사이에 값 구분 기호(쉼표)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-254">If there is more than one EII, there are value-separators (commas) between the array records.</span></span> <span data-ttu-id="37668-255">그 다음에 끝 배열이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37668-255">All this is followed by an end-array.</span></span><br /><br /> <span data-ttu-id="37668-256">예제: 다음 XML 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-256">Example: The following XML element maps to a JSON fragment.</span></span><br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> <span data-ttu-id="37668-257">JSON 조각은 ["aaa","bbb"]입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-257">The JSON fragment is ["aaa","bbb"]</span></span><br /><br /> <span data-ttu-id="37668-258">공백(`ws`)은 배열에 대한 XML과 JSON 간 매핑에서 생성되지 않고 JSON과 XML 간 매핑에서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-258">Whitespace (`ws`) is never generated on XML to JSON mapping for arrays and is ignored on JSON to XML mapping.</span></span><br /><br /> <span data-ttu-id="37668-259">예제: AJSON 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-259">Example: AJSON fragment.</span></span><br /><br /> <span data-ttu-id="37668-260">[     "aaa",     "bbb"]</span><span class="sxs-lookup"><span data-stu-id="37668-260">[     "aaa",     "bbb"]</span></span><br /><br /> <span data-ttu-id="37668-261">매핑할 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-261">The XML element that it maps to.</span></span><br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|  
  
 <span data-ttu-id="37668-262">멤버 레코드는 다음과 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-262">Member Records work as follows:</span></span>  
  
-   <span data-ttu-id="37668-263">내부 요소의 [local name]은 JSON RFC의 섹션 2.2에 정의된 대로 `string`의 `member` 일부에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-263">Inner element’s [local name] maps to the `string` part of the `member` as defined in section 2.2 of the JSON RFC.</span></span>  
  
 <span data-ttu-id="37668-264">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-264">Example: The following element maps to a JSON fragment.</span></span>  
  
 `<root type="object"/>`  
  
 `<myLocalName type="string">aaa</myLocalName>`  
  
 `</root >`  
  
 <span data-ttu-id="37668-265">다음 JSON 조각이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-265">The following JSON fragment is displayed.</span></span>  
  
 `{"myLocalName":"aaa"}`  
  
-   <span data-ttu-id="37668-266">XML과 JSON 간 매핑에서는 JSON에서 이스케이프해야 하는 문자가 이스케이프되고 그외 다른 문자는 이스케이프되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-266">On the XML to JSON mapping, the characters that must be escaped in JSON are escaped, and the others are not escaped.</span></span> <span data-ttu-id="37668-267">"/" 문자는 이스케이프해야 하는 문자가 아니지만 이스케이프됩니다(이 문자는 JSON과 XML 간 매핑에서는 이스케이프하지 않아도 됨).</span><span class="sxs-lookup"><span data-stu-id="37668-267">The "/" character, even though it is not a character that must be escaped, is escaped nevertheless (it does not have to be escaped on JSON to XML mapping).</span></span> <span data-ttu-id="37668-268">이것은 JSON에서 `DateTime` 데이터에 대한 ASP.NET AJAX 형식을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-268">This is required to support the ASP.NET AJAX format for `DateTime` data in JSON.</span></span>  
  
-   <span data-ttu-id="37668-269">JSON과 XML 간 매핑에서 필요한 경우 이스케이프되지 않은 문자를 포함하여 모든 문자가 [local name]을 생성하는 `string`을 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-269">On the JSON to XML mapping, all characters (including the not escaped characters, if necessary) are taken to form a `string` that produces a [local name].</span></span>  
  
-   <span data-ttu-id="37668-270">내부 요소 [children]은 `JSON Type Attribute`와 마찬가지로 `Root JSON Element`에 따라 섹션 2.2의 값에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-270">Inner elements [children] map to the value in section 2.2, according to the `JSON Type Attribute` just like for the `Root JSON Element`.</span></span> <span data-ttu-id="37668-271">여러 수준의 EII 중첩(배열 내의 중첩 포함)이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-271">Multiple levels of nesting of EIIs (including nesting within arrays) are allowed.</span></span>  
  
 <span data-ttu-id="37668-272">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-272">Example: The following element maps to a JSON fragment.</span></span>  
  
 `<root type="object">`  
  
 `<myLocalName1 type="string">myValue1</myLocalName1>`  
  
 `<myLocalName2 type="number">2</myLocalName2>`  
  
 `<myLocalName3 type="object">`  
  
 `<myNestedName1 type="boolean">true</myNestedName1>`  
  
 `<myNestedName2 type="null"/>`  
  
 `</myLocalName3>`  
  
 `</root >`  
  
 <span data-ttu-id="37668-273">다음 JSON 조각은 매핑할 JSON 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-273">The following JSON fragment is what it maps to.</span></span>  
  
 `{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}`  
  
> [!NOTE]
>  <span data-ttu-id="37668-274">앞의 매핑에는 XML 인코딩 단계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-274">There is no XML encoding step in the preceding mapping.</span></span> <span data-ttu-id="37668-275">따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 키 이름의 모든 문자가 XML 요소 이름에서 유효한 문자인 JSON 문서만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-275">Therefore, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only supports JSON documents where all characters in key names are valid characters in XML element names.</span></span> <span data-ttu-id="37668-276">예를 들어 JSON 문서 {"<":"a"}는 <가 XML 요소에 유효한 이름이 아니므로 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-276">For example, the JSON document {"<":"a"} is not supported because < is not a valid name for an XML element.</span></span>  
  
 <span data-ttu-id="37668-277">반대 상황(XML에서 유효하지만 JSON에서는 유효하지 않은 문자)의 경우 앞의 매핑에 JSON 이스케이프/이스케이프 취소 단계가 포함되므로 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-277">The reverse situation (characters valid in XML but not in JSON) does not cause any problems because the preceding mapping includes JSON escaping/unescaping steps.</span></span>  
  
 <span data-ttu-id="37668-278">배열 레코드는 다음과 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-278">Array Records work as follows:</span></span>  
  
-   <span data-ttu-id="37668-279">내부 요소의 [local name]은 "item"입니다.</span><span class="sxs-lookup"><span data-stu-id="37668-279">Inner element’s [local name] is "item".</span></span>  
  
-   <span data-ttu-id="37668-280">내부 요소의 [children]은 루트 JSON 요소에 대해 매핑되는 것과 마찬가지로 JSON 형식 특성에 따라 섹션 2.3의 값에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-280">Inner element’s [children] map to the value in section 2.3, according to the JSON Type Attribute as is does for the Root JSON Element.</span></span> <span data-ttu-id="37668-281">여러 수준의 EII 중첩(개체 내의 중첩 포함)이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="37668-281">Multiple levels of nesting of EIIs (including nesting within objects) are allowed.</span></span>  
  
 <span data-ttu-id="37668-282">예제: 다음 요소는 JSON 조각에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="37668-282">Example: The following element maps to a JSON fragment.</span></span>  
  
 `<root type="array"/>`  
  
 `<item type="string">myValue1</item>`  
  
 `<item type="number">2</item>`  
  
 `<item type="array">`  
  
 `<item type="boolean">true</item>`  
  
 `<item type="null"/>`  
  
 `</item>`  
  
 `</root >`  
  
 <span data-ttu-id="37668-283">JSON 조각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37668-283">The following is the JSON fragment.</span></span>  
  
 `["myValue1",2,[true,null]]`  
  
## <a name="see-also"></a><span data-ttu-id="37668-284">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37668-284">See Also</span></span>  
 <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>  
 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
 [<span data-ttu-id="37668-285">독립 실행형 JSON Serialization</span><span class="sxs-lookup"><span data-stu-id="37668-285">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
