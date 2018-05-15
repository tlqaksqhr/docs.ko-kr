---
title: 스타일시트 매개 변수 및 확장명 개체의 XsltArgumentList
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: de2f0dce-6b98-4908-bba7-ed150cc50355
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 808d21ae0eabdc7502ef97facc3d45f2220883af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xsltargumentlist-for-style-sheet-parameters-and-extension-objects"></a><span data-ttu-id="0a92b-102">스타일시트 매개 변수 및 확장명 개체의 XsltArgumentList</span><span class="sxs-lookup"><span data-stu-id="0a92b-102">XsltArgumentList for Style Sheet Parameters and Extension Objects</span></span>
<span data-ttu-id="0a92b-103"><xref:System.Xml.Xsl.XsltArgumentList> 클래스에는 XSLT(Extensible Stylesheet Language for Transformations) 매개 변수와 XSLT 확장 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-103">The <xref:System.Xml.Xsl.XsltArgumentList> class contains Extensible Stylesheet Language for Transformations (XSLT) parameters and XSLT extension objects.</span></span> <span data-ttu-id="0a92b-104">이러한 매개 변수와 확장 개체는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에 전달될 경우 스타일시트에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-104">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a92b-105"><xref:System.Xml.Xsl.XslTransform> 및 <xref:System.Xml.Xsl.XsltArgumentList> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-105">The <xref:System.Xml.Xsl.XslTransform> and <xref:System.Xml.Xsl.XsltArgumentList> classes are obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="0a92b-106"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-106">You can perform XSLT transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="0a92b-107">자세한 내용은 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [XslTransform 클래스에서 마이그레이션](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a92b-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="0a92b-108"><xref:System.Xml.Xsl.XsltArgumentList> 클래스에는 XSLT 매개 변수와 XSLT 확장 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-108">The <xref:System.Xml.Xsl.XsltArgumentList> class contains XSLT parameters and XSLT extension objects.</span></span> <span data-ttu-id="0a92b-109">이러한 매개 변수와 확장 개체는 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에 전달될 경우 스타일시트에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-109">When passed into the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, these parameters and extension objects can be invoked from style sheets.</span></span>  
  
 <span data-ttu-id="0a92b-110">포함 스크립트를 사용하는 대신 개체를 전달하면 다음과 같은 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-110">The following are advantages to passing an object rather than using an embedded script:</span></span>  
  
-   <span data-ttu-id="0a92b-111">클래스 캡슐화 및 재사용에 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-111">Provides better encapsulation and reuse of classes.</span></span>  
  
-   <span data-ttu-id="0a92b-112">스타일시트를 더 작게 유지하고 보다 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-112">Allows style sheets to be smaller and more maintainable.</span></span>  
  
-   <span data-ttu-id="0a92b-113">지원되는 <xref:System> 네임스페이스의 집합 내에 정의된 네임스페이스 이외의 다른 네임스페이스에 속하는 클래스에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-113">Supports calling methods on classes belonging to namespaces other than those defined within the set of supported <xref:System> namespaces.</span></span>  
  
-   <span data-ttu-id="0a92b-114"><xref:System.Xml.XPath.XPathNodeIterator>를 사용하여 스타일시트에 결과 트리 조각을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-114">Supports passing result tree fragments to the style sheet with the use of the <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
## <a name="xslt-style-sheet-parameters"></a><span data-ttu-id="0a92b-115">XSLT 스타일시트 매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a92b-115">XSLT Style Sheet Parameters</span></span>  
 <span data-ttu-id="0a92b-116"><xref:System.Xml.Xsl.XsltArgumentList> 메서드를 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>에 XSLT 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-116">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="0a92b-117">그러면 정규화된 이름과 네임스페이스 URI(Uniform Resource Identifier)가 매개 변수 개체와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-117">A qualified name and namespace Uniform Resource Identifier (URI) are associated with the parameter object at that time.</span></span>  
  
 <span data-ttu-id="0a92b-118">매개 변수 개체는 W3C(World Wide Web 컨소시엄) 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-118">The parameter object should correspond to a World Wide Web Consortium (W3C) type.</span></span> <span data-ttu-id="0a92b-119">다음 표에서는 해당하는 W3C 형식과 해당 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 클래스(형식), 그리고 W3C 형식이 XPath(XML Path Language) 형식인지, 또는 XSLT 형식인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-119">The following table shows the corresponding W3C types, the equivalent [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes (type), and whether the W3C type is an XML Path Language (XPath) type or XSLT type.</span></span>  
  
|<span data-ttu-id="0a92b-120">W3C 형식</span><span class="sxs-lookup"><span data-stu-id="0a92b-120">W3C Type</span></span>|<span data-ttu-id="0a92b-121">해당 .NET Framework 클래스(형식)</span><span class="sxs-lookup"><span data-stu-id="0a92b-121">Equivalent .NET Framework class (type)</span></span>|<span data-ttu-id="0a92b-122">XPath 형식 또는 XSLT 형식</span><span class="sxs-lookup"><span data-stu-id="0a92b-122">XPath type or XSLT type</span></span>|  
|--------------|----------------------------------------------|-----------------------------|  
|<span data-ttu-id="0a92b-123">문자열</span><span class="sxs-lookup"><span data-stu-id="0a92b-123">String</span></span>|<span data-ttu-id="0a92b-124">System.String</span><span class="sxs-lookup"><span data-stu-id="0a92b-124">System.String</span></span>|<span data-ttu-id="0a92b-125">XPath</span><span class="sxs-lookup"><span data-stu-id="0a92b-125">XPath</span></span>|  
|<span data-ttu-id="0a92b-126">부울</span><span class="sxs-lookup"><span data-stu-id="0a92b-126">Boolean</span></span>|<span data-ttu-id="0a92b-127">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="0a92b-127">System.Boolean</span></span>|<span data-ttu-id="0a92b-128">XPath</span><span class="sxs-lookup"><span data-stu-id="0a92b-128">XPath</span></span>|  
|<span data-ttu-id="0a92b-129">수</span><span class="sxs-lookup"><span data-stu-id="0a92b-129">Number</span></span>|<span data-ttu-id="0a92b-130">System.Double</span><span class="sxs-lookup"><span data-stu-id="0a92b-130">System.Double</span></span>|<span data-ttu-id="0a92b-131">XPath</span><span class="sxs-lookup"><span data-stu-id="0a92b-131">XPath</span></span>|  
|<span data-ttu-id="0a92b-132">결과 트리 조각</span><span class="sxs-lookup"><span data-stu-id="0a92b-132">Result Tree Fragment</span></span>|<span data-ttu-id="0a92b-133">System.Xml.XPath.XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="0a92b-133">System.Xml.XPath.XPathNavigator</span></span>|<span data-ttu-id="0a92b-134">XSLT</span><span class="sxs-lookup"><span data-stu-id="0a92b-134">XSLT</span></span>|  
|<span data-ttu-id="0a92b-135">노드 집합</span><span class="sxs-lookup"><span data-stu-id="0a92b-135">Node Set</span></span>|<span data-ttu-id="0a92b-136">System.Xml.XPath.XPathNodeIterator</span><span class="sxs-lookup"><span data-stu-id="0a92b-136">System.Xml.XPath.XPathNodeIterator</span></span>|<span data-ttu-id="0a92b-137">XPath</span><span class="sxs-lookup"><span data-stu-id="0a92b-137">XPath</span></span>|  
  
 <span data-ttu-id="0a92b-138">매개 변수 개체가 위 클래스에 해당하지 않으면 Double 또는 String 형식이 적절히 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-138">If the parameter object is not one of the above classes, it is forced to either a Double or String, as appropriate.</span></span> <span data-ttu-id="0a92b-139">Int16, UInt16, Int32, UInt32, Int64, UInt64, Single 및 Decimal 형식은 Double 형식이 되며</span><span class="sxs-lookup"><span data-stu-id="0a92b-139">Int16, UInt16, Int32, UInt32, Int64, UInt64, Single and Decimal types are forced to a Double.</span></span> <span data-ttu-id="0a92b-140">기타 모든 형식은 `ToString` 메서드를 사용하여 String 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-140">All other types are forced to a String using the `ToString` method.</span></span>  
  
#### <a name="to-use-the-xslt-parameter-the-user-needs-to-do-the-following"></a><span data-ttu-id="0a92b-141">XSLT 매개 변수를 사용하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-141">To use the XSLT parameter, the user needs to do the following:</span></span>  
  
1.  <span data-ttu-id="0a92b-142"><xref:System.Xml.Xsl.XsltArgumentList>을 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>를 만들고 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-142">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the objects using <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.</span></span>  
  
2.  <span data-ttu-id="0a92b-143">스타일시트에서 매개 변수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-143">Call the parameters from the style sheet.</span></span>  
  
3.  <span data-ttu-id="0a92b-144"><xref:System.Xml.Xsl.XsltArgumentList>를 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-144">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0a92b-145">예</span><span class="sxs-lookup"><span data-stu-id="0a92b-145">Example</span></span>  
 <span data-ttu-id="0a92b-146">다음 예제에서는 <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> 메서드를 사용하여 계산된 할인 기간을 유지하는 매개 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-146">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold a calculated discount date.</span></span> <span data-ttu-id="0a92b-147">할인 기간은 주문 날짜로부터 20일 동안으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-147">The discount date is calculated to be 20 days from the order date.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public class Sample  
  
   Private Const filename As String = "order.xml"  
   Private Const stylesheet As String = "discount.xsl"  
  
   Public Shared Sub Main()  
  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Calculate the discount date.  
    Dim today As DateTime = DateTime.Now  
    Dim d As DateTime = today.AddDays(20)  
    xslArg.AddParam("discount", "", d.ToString())  
  
    'Create an XmlTextWriter to handle the output.  
    Dim writer As XmlTextWriter = New XmlTextWriter("orderout.xml", Nothing)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
  
    writer.Close()  
  
  End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "order.xml";  
   private const String stylesheet = "discount.xsl";  
  
   public static void Main() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Calculate the discount date.  
    DateTime today = DateTime.Now;  
    DateTime d = today.AddDays(20);  
    xslArg.AddParam("discount", "", d.ToString());  
  
    //Create an XmlTextWriter to handle the output.  
    XmlTextWriter writer = new XmlTextWriter("orderout.xml", null);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="0a92b-148">입력</span><span class="sxs-lookup"><span data-stu-id="0a92b-148">Input</span></span>  
 <span data-ttu-id="0a92b-149">order.xml</span><span class="sxs-lookup"><span data-stu-id="0a92b-149">order.xml</span></span>  
  
```xml  
<!--Represents a customer order-->  
<order>  
  <book ISBN='10-861003-324'>  
    <title>The Handmaid's Tale</title>  
    <price>19.95</price>  
  </book>  
  <cd ISBN='2-3631-4'>  
    <title>Americana</title>  
    <price>16.95</price>  
  </cd>  
</order>  
```  
  
 <span data-ttu-id="0a92b-150">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="0a92b-150">discount.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">  
  <xsl:param name="discount"/>  
  <xsl:template match="/">  
    <order>  
      <xsl:variable name="sub-total" select="sum(//price)"/>  
      <total><xsl:value-of select="$sub-total"/></total>  
      15% discount if paid by: <xsl:value-of select="$discount"/>  
    </order>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a><span data-ttu-id="0a92b-151">출력</span><span class="sxs-lookup"><span data-stu-id="0a92b-151">Output</span></span>  
  
```xml  
<order>  
   <total>36.9</total>   
   15% discount if paid by: 5/6/2001 5:01:15 PM   
</order>  
```  
  
## <a name="xslt-extension-objects"></a><span data-ttu-id="0a92b-152">XSLT 확장 개체</span><span class="sxs-lookup"><span data-stu-id="0a92b-152">XSLT Extension Objects</span></span>  
 <span data-ttu-id="0a92b-153"><xref:System.Xml.Xsl.XsltArgumentList> 메서드를 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>에 XSLT 확장 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-153">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="0a92b-154">이 때 정규화된 이름과 네임스페이스 URI가 확장 개체와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-154">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
 <span data-ttu-id="0a92b-155">개체가 추가될 때 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>의 호출자는 보안 정책에서 완전히 신뢰되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-155">When an object is added, the caller of the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> must be fully trusted in the security policy.</span></span> <span data-ttu-id="0a92b-156">호출자가 일부 신뢰되는 경우에는 추가 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-156">If the caller is semi-trusted, the addition will fail.</span></span>  
  
 <span data-ttu-id="0a92b-157">개체가 추가되더라도 성공적으로 실행된다고 보장할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-157">Though an object is added successfully, it does not guarantee that the execution will be successful.</span></span> <span data-ttu-id="0a92b-158"><xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드가 호출되면 <xref:System.Xml.Xsl.XslTransform.Load%2A> 시 제공된 증명 정보에 따라 권한이 판별되어 해당 권한 집합이 전체 변환 프로세스에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-158">When the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is called, permissions are calculated against the evidence provided at <xref:System.Xml.Xsl.XslTransform.Load%2A> time, and that permission set is assigned to the entire transformation process.</span></span> <span data-ttu-id="0a92b-159">확장 개체가 해당 권한 집합에 없는 권한을 요구하는 작업을 시작하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-159">If an extension object attempts to initiate an action that requires permissions not found in the set, an exception is thrown.</span></span>  
  
 <span data-ttu-id="0a92b-160">확장 개체에서 반환된 데이터 형식은 네 가지 기본 XPath 데이터 형식인 숫자, 문자열, 부울 및 노드 집합 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-160">The data types returned from extension objects are one of the four basic XPath data types of number, string, Boolean, and node set.</span></span>  
  
#### <a name="to-use-the-xslt-extension-object-the-user-needs-to-do-the-following"></a><span data-ttu-id="0a92b-161">XSLT 확장 개체를 사용하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-161">To use the XSLT extension object, the user needs to do the following:</span></span>  
  
1.  <span data-ttu-id="0a92b-162"><xref:System.Xml.Xsl.XsltArgumentList>를 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>를 만들고 확장 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-162">Create an <xref:System.Xml.Xsl.XsltArgumentList> and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A>.</span></span>  
  
2.  <span data-ttu-id="0a92b-163">스타일시트에서 확장명 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-163">Invoke the extension object from the style sheet.</span></span>  
  
3.  <span data-ttu-id="0a92b-164"><xref:System.Xml.Xsl.XsltArgumentList>를 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-164">Pass the <xref:System.Xml.Xsl.XsltArgumentList> to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0a92b-165">예</span><span class="sxs-lookup"><span data-stu-id="0a92b-165">Example</span></span>  
 <span data-ttu-id="0a92b-166">다음 예제에서는 반지름이 주어진 원의 원주를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0a92b-166">The following example calculates the circumference of a circle given its radius.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.XPath  
Imports System.Xml.Xsl  
  
Public Class Sample  
   Private Const filename As String = "number.xml"  
   Private Const stylesheet As String = "circle.xsl"  
  
   Public Shared Sub Main()  
        Dim test As Sample = New Sample  
   End Sub  
  
  Public Sub New()  
    'Create the XslTransform and load the style sheet.  
    Dim xslt As XslTransform = New XslTransform  
    xslt.Load(stylesheet)  
  
    'Load the XML data file.  
    Dim doc As XPathDocument = New XPathDocument(filename)  
  
    'Create an XsltArgumentList.  
    Dim xslArg As XsltArgumentList = New XsltArgumentList  
  
    'Add an object to calculate the circumference of the circle.  
    Dim obj As Calculate = New Calculate  
    xslArg.AddExtensionObject("urn:myObj", obj)  
  
    'Create an XmlTextWriter to output to the console.  
    Dim writer As XmlTextWriter = New XmlTextWriter(Console.Out)  
  
    'Transform the file.  
    xslt.Transform(doc, xslArg, writer, Nothing)  
    writer.Close()  
  
  End Sub  
  
  'Calculates the circumference of a circle given the radius.  
  Public Class Calculate  
  
    Private circ As double = 0  
  
    Public Function Circumference(radius As Double) As Double  
       circ = Math.PI*2*radius  
       Return circ  
    End Function  
  End Class  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
public class Sample  
{  
   private const String filename = "number.xml";  
   private const String stylesheet = "circle.xsl";  
  
   public static void Main() {  
  
        Sample test = new Sample();  
    }  
  
  public Sample() {  
  
    //Create the XslTransform and load the style sheet.  
    XslTransform xslt = new XslTransform();  
    xslt.Load(stylesheet);  
  
    //Load the XML data file.  
    XPathDocument doc = new XPathDocument(filename);  
  
    //Create an XsltArgumentList.  
    XsltArgumentList xslArg = new XsltArgumentList();  
  
    //Add an object to calculate the circumference of the circle.  
    Calculate obj = new Calculate();  
    xslArg.AddExtensionObject("urn:myObj", obj);  
  
    //Create an XmlTextWriter to output to the console.  
    XmlTextWriter writer = new XmlTextWriter(Console.Out);  
  
    //Transform the file.  
    xslt.Transform(doc, xslArg, writer, null);  
    writer.Close();  
  
  }  
  
  //Calculates the circumference of a circle given the radius.  
  public class Calculate{  
  
    private double circ = 0;  
  
    public double Circumference(double radius){  
       circ = Math.PI*2*radius;  
       return circ;  
    }  
  }  
}  
```  
  
### <a name="input"></a><span data-ttu-id="0a92b-167">입력</span><span class="sxs-lookup"><span data-stu-id="0a92b-167">Input</span></span>  
 <span data-ttu-id="0a92b-168">number.xml</span><span class="sxs-lookup"><span data-stu-id="0a92b-168">number.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<data>  
  <circle>  
    <radius>12</radius>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
  </circle>  
</data>    
```  
  
 <span data-ttu-id="0a92b-169">circle.xsl</span><span class="sxs-lookup"><span data-stu-id="0a92b-169">circle.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
    xmlns:myObj="urn:myObj">  
  
  <xsl:template match="data">  
  <circles>  
  <xsl:for-each select="circle">  
    <circle>  
    <xsl:copy-of select="node()"/>  
       <circumference>  
          <xsl:value-of select="myObj:Circumference(radius)"/>          
       </circumference>  
    </circle>  
  </xsl:for-each>  
  </circles>  
  </xsl:template>  
</xsl:stylesheet>  
```  
  
### <a name="output"></a><span data-ttu-id="0a92b-170">출력</span><span class="sxs-lookup"><span data-stu-id="0a92b-170">Output</span></span>  
 `<circles xmlns:myObj="urn:myObj">`  
  
 `<circle>`  
  
 `<radius>12</radius>`  
  
 `<circumference>75.398223686155</circumference>`  
  
 `</circle>`  
  
 `<circle>`  
  
 `<radius>37.5</radius>`  
  
 `<circumference>235.61944901923448</circumference>`  
  
 `</circle>`  
  
 `</circles>`  
  
## <a name="see-also"></a><span data-ttu-id="0a92b-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a92b-171">See Also</span></span>  
 [<span data-ttu-id="0a92b-172">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="0a92b-172">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
