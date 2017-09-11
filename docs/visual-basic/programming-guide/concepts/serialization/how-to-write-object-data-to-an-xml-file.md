---
title: "방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기 | Microsoft 문서"
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
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
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
ms.openlocfilehash: 27131f357c1f5afc75645bff88ae5d7cd2395617
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="f0bc5-102">방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기</span><span class="sxs-lookup"><span data-stu-id="f0bc5-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="f0bc5-103">이 예제에서는 클래스에서 <xref:System.Xml.Serialization.XmlSerializer>클래스</xref:System.Xml.Serialization.XmlSerializer> 를 사용 하 여 XML 파일에는 개체를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-103">TThis example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0bc5-104">예제</span><span class="sxs-lookup"><span data-stu-id="f0bc5-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f0bc5-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f0bc5-105">Compiling the Code</span></span>  
 <span data-ttu-id="f0bc5-106">클래스에는 매개 변수 없는 공용 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f0bc5-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f0bc5-107">Robust Programming</span></span>  
 <span data-ttu-id="f0bc5-108">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f0bc5-109">Serialize 되는 클래스에 매개 변수가 없는 공용 생성자가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="f0bc5-110">파일이 존재 하 고는 읽기 전용 (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="f0bc5-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="f0bc5-111">경로가 너무 깁니다 (<xref:System.IO.PathTooLongException>).</xref:System.IO.PathTooLongException></span><span class="sxs-lookup"><span data-stu-id="f0bc5-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="f0bc5-112">디스크가 꽉 찼습니다 (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="f0bc5-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f0bc5-113">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="f0bc5-113">.NET Framework Security</span></span>  
 <span data-ttu-id="f0bc5-114">이 예제 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="f0bc5-115">응용 프로그램 파일을 만드는 경우, 해당 응용 프로그램 필요 `Create` 폴더에 대 한 액세스.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="f0bc5-116">응용 프로그램에만 필요한 파일이 이미 있으면, `Write` 액세스, 낮은 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="f0bc5-117">가능한 경우, 것이 더 안전을 배포 하는 동안 파일을 만들고만 권한을 부여 `Read` 단일 파일에 대 한 액세스 하지 않고 `Create` 폴더에 대 한 액세스.</span><span class="sxs-lookup"><span data-stu-id="f0bc5-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0bc5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0bc5-118">See Also</span></span>  
 <span data-ttu-id="f0bc5-119"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="f0bc5-119"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="f0bc5-120"> [방법: XML 파일 (Visual Basic)에서 개체 데이터 읽기](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="f0bc5-120"> [How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span></span>  
<span data-ttu-id="f0bc5-121"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span><span class="sxs-lookup"><span data-stu-id="f0bc5-121"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span></span>
