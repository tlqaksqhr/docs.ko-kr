---
title: "방법: XML 파일에서 개체 데이터 읽기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6a3389de2f3272a546a7380ef386f5d88666e6d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="befd7-102">방법: XML 파일에서 개체 데이터 읽기(C#)</span><span class="sxs-lookup"><span data-stu-id="befd7-102">How to: Read Object Data from an XML File (C#)</span></span>
<span data-ttu-id="befd7-103">이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 이전에 XML 파일에 기록된 개체 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="befd7-104">예제</span><span class="sxs-lookup"><span data-stu-id="befd7-104">Example</span></span>  
  
```csharp  
public class Book  
{  
    public String title;  
}         
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =   
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="befd7-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="befd7-105">Compiling the Code</span></span>  
 <span data-ttu-id="befd7-106">파일 이름 "c:\temp\SerializationOverview.xml"을 serialize된 데이터가 포함된 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="befd7-107">데이터를 serialize하는 작업에 대한 자세한 내용은 [방법: XML 파일에 개체 데이터 쓰기(C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="befd7-107">For more information about serializing data, see [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="befd7-108">클래스에는 매개 변수가 없는 public 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="befd7-109">public 속성과 필드만 deserialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="befd7-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="befd7-110">Robust Programming</span></span>  
 <span data-ttu-id="befd7-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="befd7-112">serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="befd7-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="befd7-113">파일의 데이터가 deserialize할 클래스의 데이터를 나타내지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="befd7-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="befd7-114">파일이 없는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="befd7-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="befd7-115">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="befd7-115">.NET Framework Security</span></span>  
 <span data-ttu-id="befd7-116">항상 입력을 확인하고, 신뢰할 수 없는 소스의 데이터를 deserialize하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="befd7-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="befd7-117">다시 생성된 개체는 deserialize한 코드의 사용 권한으로 로컬 컴퓨터에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="befd7-118">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="befd7-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befd7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="befd7-119">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 [<span data-ttu-id="befd7-120">방법: XML 파일에 개체 데이터 쓰기(C#)</span><span class="sxs-lookup"><span data-stu-id="befd7-120">How to: Write Object Data to an XML File (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)  
 [<span data-ttu-id="befd7-121">serialization(C#)</span><span class="sxs-lookup"><span data-stu-id="befd7-121">Serialization (C# )</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)  
 [<span data-ttu-id="befd7-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="befd7-122">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
