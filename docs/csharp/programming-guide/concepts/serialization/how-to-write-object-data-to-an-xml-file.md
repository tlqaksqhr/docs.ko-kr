---
title: '방법: XML 파일에 개체 데이터 쓰기(C#)'
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 1c8bfd00452cee63456bc3bf64ccf4a0c61aa06e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="396a3-102">방법: XML 파일에 개체 데이터 쓰기(C#)</span><span class="sxs-lookup"><span data-stu-id="396a3-102">How to: Write Object Data to an XML File (C#)</span></span>
<span data-ttu-id="396a3-103">이 예제에서는 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용하여 XML 파일에 클래스의 개체를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="396a3-104">예</span><span class="sxs-lookup"><span data-stu-id="396a3-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;   
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =   
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="396a3-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="396a3-105">Compiling the Code</span></span>  
 <span data-ttu-id="396a3-106">클래스에는 매개 변수가 없는 public 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="396a3-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="396a3-107">Robust Programming</span></span>  
 <span data-ttu-id="396a3-108">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="396a3-109">serialize되는 클래스에 매개 변수가 없는 public 생성자가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="396a3-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="396a3-110">파일이 있지만 읽기 전용인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="396a3-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="396a3-111">경로가 너무 긴 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="396a3-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="396a3-112">디스크가 꽉 찬 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="396a3-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="396a3-113">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="396a3-113">.NET Framework Security</span></span>  
 <span data-ttu-id="396a3-114">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="396a3-115">응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램에 폴더에 대한 `Create` 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="396a3-116">파일이 이미 있는 경우 응용 프로그램에 더 낮은 권한인 `Write` 권한만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="396a3-117">가능한 경우 배포하는 동안 파일을 만들고, 폴더에 대한 `Create` 권한 대신 단일 파일에 대해 `Read` 권한만 부여하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="396a3-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="396a3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="396a3-118">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 [<span data-ttu-id="396a3-119">방법: XML 파일에서 개체 데이터 읽기(C#)</span><span class="sxs-lookup"><span data-stu-id="396a3-119">How to: Read Object Data from an XML File (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [<span data-ttu-id="396a3-120">serialization(C#)</span><span class="sxs-lookup"><span data-stu-id="396a3-120">Serialization (C# )</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)
