---
title: "문자열을 .NET Framework 데이터 형식으로 변환"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="d061f-102">문자열을 .NET Framework 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d061f-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="d061f-103">사용 하 여 문자열을.NET Framework 데이터 형식으로 변환 하려는 경우는 **XmlConvert** 응용 프로그램 요구 사항에 맞는 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="d061f-104">사용 가능한 변환 메서드의 전체 목록은 **XmlConvert** 클래스를 참조 하십시오. <xref:System.Xml.XmlConvert>합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="d061f-105">반환 된 문자열의 **ToString** 방법은에 전달 되는 데이터의 문자열 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="d061f-106">또한를 사용 하 여 변환 하는.NET Framework 유형도 몇 가지는 **XmlConvert** 클래스의 메서드는 사용 하지 않도록 아직는 **System.Convert** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="d061f-107">**XmlConvert** 클래스 XSD (XML 스키마) 데이터 형식 사양을 따르며에 데이터 형식이 있는 **XmlConvert** 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="d061f-108">다음 표에서는 XSD(XML 스키마) 데이터 형식 매핑을 사용할 때 반환되는 .NET Framework 데이터 형식 및 문자열 형식의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="d061f-109">이러한.NET Framework 형식을 사용 하 여 처리할 수 없습니다 **System.Convert**합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="d061f-110">.NET Framework 형식</span><span class="sxs-lookup"><span data-stu-id="d061f-110">.NET Framework type</span></span>|<span data-ttu-id="d061f-111">반환 문자열</span><span class="sxs-lookup"><span data-stu-id="d061f-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="d061f-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="d061f-112">Boolean</span></span>|<span data-ttu-id="d061f-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="d061f-113">"true", "false"</span></span>|  
|<span data-ttu-id="d061f-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="d061f-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-115">"INF"</span></span>|  
|<span data-ttu-id="d061f-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="d061f-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-117">"-INF"</span></span>|  
|<span data-ttu-id="d061f-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="d061f-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-119">"INF"</span></span>|  
|<span data-ttu-id="d061f-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="d061f-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-121">"-INF"</span></span>|  
|<span data-ttu-id="d061f-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="d061f-122">DateTime</span></span>|<span data-ttu-id="d061f-123">형식은 "yyyy-MM-ddTHH:mm:sszzzzzz" 및 해당 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="d061f-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="d061f-124">Timespan</span></span>|<span data-ttu-id="d061f-125">형식은 PnYnMnTnHnMnS입니다. 즉, `P2Y10M15DT10H30M20S`는 2년 10개월 15일 10시간 30분 20초의 지속 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d061f-126">테이블을 사용 하 여 문자열에 나열 된.NET Framework 형식으로 변환 하는 경우는 **ToString** 메서드에서 반환 된 문자열은 기본 형식이 아니라 XSD (XML 스키마) 문자열 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="d061f-127">**DateTime** 및 **Timespan** 하의 값 형식은 다릅니다. 한 **DateTime** 반면은 순간적인 시각을 나타내며는 **TimeSpan** 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="d061f-128">**DateTime** 및 **Timespan** 형식을 XSD (XML 스키마) 데이터 형식 사양에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="d061f-129">예:</span><span class="sxs-lookup"><span data-stu-id="d061f-129">For example:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 <span data-ttu-id="d061f-130">**출력**</span><span class="sxs-lookup"><span data-stu-id="d061f-130">**Output**</span></span>  
  
 <span data-ttu-id="d061f-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="d061f-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="d061f-132">다음 코드는 정수를 문자열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-132">The following code converts an integer to a string:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 <span data-ttu-id="d061f-133">**출력**</span><span class="sxs-lookup"><span data-stu-id="d061f-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="d061f-134">그러나 문자열을 변환 하는 경우 **부울**, **단일**, 또는 **Double**, 반환 되는.NET Framework 형식을 사용 하는 경우 반환 되는 형식 동일 하지 않습니다는 **System.Convert** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="d061f-135">문자열을 Boolean 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d061f-135">String to Boolean</span></span>  
 <span data-ttu-id="d061f-136">다음 표에서 문자열을 변환 하는 경우 지정된 된 입력된 문자열에 대해 생성 되는 형식을 보여 줍니다. **부울** 를 사용 하 여 **ToBoolean** 메서드.</span><span class="sxs-lookup"><span data-stu-id="d061f-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="d061f-137">유효한 문자열 입력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d061f-137">Valid string input parameter</span></span>|<span data-ttu-id="d061f-138">.NET Framework 출력 형식</span><span class="sxs-lookup"><span data-stu-id="d061f-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="d061f-139">"true"</span><span class="sxs-lookup"><span data-stu-id="d061f-139">"true"</span></span>|<span data-ttu-id="d061f-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="d061f-140">Boolean.True</span></span>|  
|<span data-ttu-id="d061f-141">"1"</span><span class="sxs-lookup"><span data-stu-id="d061f-141">"1"</span></span>|<span data-ttu-id="d061f-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="d061f-142">Boolean.True</span></span>|  
|<span data-ttu-id="d061f-143">"false"</span><span class="sxs-lookup"><span data-stu-id="d061f-143">"false"</span></span>|<span data-ttu-id="d061f-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="d061f-144">Boolean.False</span></span>|  
|<span data-ttu-id="d061f-145">"0"</span><span class="sxs-lookup"><span data-stu-id="d061f-145">"0"</span></span>|<span data-ttu-id="d061f-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="d061f-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="d061f-147">예를 들어, 다음과 같이 XML을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="d061f-148">**입력**</span><span class="sxs-lookup"><span data-stu-id="d061f-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 <span data-ttu-id="d061f-149">다음 코드를 인식할 수 있는 둘 다 고 **bvalue** 은 **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="d061f-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="d061f-150">문자열을 Single 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d061f-150">String to Single</span></span>  
 <span data-ttu-id="d061f-151">다음 표에서 문자열을 변환 하는 경우 지정된 된 입력된 문자열에 대해 생성 되는 형식을 보여 줍니다.는 **단일** 를 사용 하는 **ToSingle** 메서드.</span><span class="sxs-lookup"><span data-stu-id="d061f-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="d061f-152">유효한 문자열 입력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d061f-152">Valid string input parameter</span></span>|<span data-ttu-id="d061f-153">.NET Framework 출력 형식</span><span class="sxs-lookup"><span data-stu-id="d061f-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="d061f-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-154">"INF"</span></span>|<span data-ttu-id="d061f-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="d061f-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-156">"-INF"</span></span>|<span data-ttu-id="d061f-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="d061f-158">문자열을 Double 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="d061f-158">String to Double</span></span>  
 <span data-ttu-id="d061f-159">다음 표에서 문자열을 변환 하는 경우 지정된 된 입력된 문자열에 대해 생성 되는 형식을 보여 줍니다.는 **단일** 를 사용 하는 **ToDouble** 메서드.</span><span class="sxs-lookup"><span data-stu-id="d061f-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="d061f-160">유효한 문자열 입력 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d061f-160">Valid string input parameter</span></span>|<span data-ttu-id="d061f-161">.NET Framework 출력 형식</span><span class="sxs-lookup"><span data-stu-id="d061f-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="d061f-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-162">"INF"</span></span>|<span data-ttu-id="d061f-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="d061f-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="d061f-164">"-INF"</span></span>|<span data-ttu-id="d061f-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="d061f-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="d061f-166">다음 코드는 `<Infinity>INF</Infinity>`를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d061f-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="d061f-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d061f-167">See Also</span></span>  
 [<span data-ttu-id="d061f-168">XML 데이터 형식 변환</span><span class="sxs-lookup"><span data-stu-id="d061f-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="d061f-169">.NET Framework 형식을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="d061f-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
