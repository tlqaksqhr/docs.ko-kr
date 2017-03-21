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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c448d79a88517925712f79ed061aa90933e3f6d1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>방법: XML 파일 (Visual Basic)에서 개체 데이터 읽기
이 예제에서는 이전에 <xref:System.Xml.Serialization.XmlSerializer>클래스</xref:System.Xml.Serialization.XmlSerializer> 를 사용 하 여 XML 파일에 기록 된 개체 데이터를 읽습니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
 파일 이름 "c:\temp\SerializationOverview.xml을" serialize 된 데이터를 포함 하는 파일의 이름을 바꿉니다. 데이터를 직렬화 하는 작업에 대 한 자세한 내용은 참조 [하는 방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)합니다.  
  
 클래스에는 매개 변수 없는 공용 생성자가 있어야 합니다.  
  
 Public 속성 및 필드 deserialize 됩니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   Serialize 되는 클래스에 매개 변수가 없는 공용 생성자가 없는 합니다.  
  
-   파일의 데이터를 deserialize 할 클래스에서 데이터를 표시 하지 않습니다.  
  
-   파일이 존재 하지 않습니다 (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 항상 입력이를 확인 하 고 신뢰할 수 없는 소스에서 데이터를 deserialize 하지 마십시오. 다시 생성된 된 개체를 deserialize 하는 코드의 사용 권한 가진 로컬 컴퓨터에서 실행 됩니다. 응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IO.StreamWriter></xref:System.IO.StreamWriter>   
 [방법: XML 파일 (Visual Basic)에 개체 데이터 쓰기](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)   
 [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)
