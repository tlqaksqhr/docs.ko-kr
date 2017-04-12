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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 146ccb7b1999049106d5f0be1ce78e740dfcf060
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a>방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기
이 예제에서는 클래스에서 <xref:System.Xml.Serialization.XmlSerializer>클래스</xref:System.Xml.Serialization.XmlSerializer> 를 사용 하 여 XML 파일에는 개체를 씁니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
 클래스에는 매개 변수 없는 공용 생성자가 있어야 합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   Serialize 되는 클래스에 매개 변수가 없는 공용 생성자가 없는 합니다.  
  
-   파일이 존재 하 고는 읽기 전용 (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
-   경로가 너무 깁니다 (<xref:System.IO.PathTooLongException>).</xref:System.IO.PathTooLongException>  
  
-   디스크가 꽉 찼습니다 (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 이 예제 파일이 아직 없는 경우 새 파일을 만듭니다. 응용 프로그램 파일을 만드는 경우, 해당 응용 프로그램 필요 `Create` 폴더에 대 한 액세스. 응용 프로그램에만 필요한 파일이 이미 있으면, `Write` 액세스, 낮은 권한입니다. 가능한 경우, 것이 더 안전을 배포 하는 동안 파일을 만들고만 권한을 부여 `Read` 단일 파일에 대 한 액세스 하지 않고 `Create` 폴더에 대 한 액세스.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StreamWriter></xref:System.IO.StreamWriter>   
 [방법: XML 파일 (Visual Basic)에서 개체 데이터 읽기](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)   
 [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
