---
title: "방법: XML 파일 (Visual Basic)에서 개체 데이터 읽기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b9697f763a2d781c37960d46cbc7fa4536c84b4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="fcbe8-102">방법: XML 파일 (Visual Basic)에서 개체 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="fcbe8-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="fcbe8-103">이 예제에서는 이전에 <xref:System.Xml.Serialization.XmlSerializer>클래스</xref:System.Xml.Serialization.XmlSerializer> 를 사용 하 여 XML 파일에 기록 된 개체 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcbe8-104">예제</span><span class="sxs-lookup"><span data-stu-id="fcbe8-104">Example</span></span>  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fcbe8-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fcbe8-105">Compiling the Code</span></span>  
 <span data-ttu-id="fcbe8-106">파일 이름 "c:\temp\SerializationOverview.xml을" serialize 된 데이터를 포함 하는 파일의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="fcbe8-107">데이터를 직렬화 하는 작업에 대 한 자세한 내용은 참조 [하는 방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="fcbe8-108">클래스에는 매개 변수 없는 공용 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="fcbe8-109">Public 속성 및 필드 deserialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fcbe8-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fcbe8-110">Robust Programming</span></span>  
 <span data-ttu-id="fcbe8-111">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="fcbe8-112">Serialize 되는 클래스에 매개 변수가 없는 공용 생성자가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="fcbe8-113">파일의 데이터를 deserialize 할 클래스에서 데이터를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="fcbe8-114">파일이 존재 하지 않습니다 (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="fcbe8-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fcbe8-115">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="fcbe8-115">.NET Framework Security</span></span>  
 <span data-ttu-id="fcbe8-116">항상 입력이를 확인 하 고 신뢰할 수 없는 소스에서 데이터를 deserialize 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="fcbe8-117">다시 생성된 된 개체를 deserialize 하는 코드의 사용 권한 가진 로컬 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="fcbe8-118">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcbe8-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcbe8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcbe8-119">See Also</span></span>  
 <span data-ttu-id="fcbe8-120"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="fcbe8-120"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="fcbe8-121"> [방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="fcbe8-121"> [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span></span>  
<span data-ttu-id="fcbe8-122"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="fcbe8-122"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span></span>  
<span data-ttu-id="fcbe8-123"> [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="fcbe8-123"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md)</span></span>
