---
title: "LINQ 및 파일 디렉터리 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
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
ms.openlocfilehash: 5536ae95b42cdaddda2c4cae97a114681e94b0ab
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-file-directories-visual-basic"></a>LINQ 및 파일 디렉터리 (Visual Basic)
많은 파일 시스템 작업 기본적으로 쿼리는 LINQ 사용 하는 것이 적합 하며 합니다.  
  
 이 섹션에서는 쿼리 비파괴 되었는지 확인 합니다. 원본 파일이 나 폴더의 내용을 변경 하는 사용 되지 않습니다. 이 쿼리도 인해 의도 하지 않은 결과가 발생 하지 않아야 하는 규칙을 따릅니다. 일반적으로 원본 데이터를 수정 하는 모든 코드 (만들기 / update / delete 연산자를 수행 하는 쿼리 포함)만 데이터를 쿼리 하는 코드와에서 별도로 유지 되어야 합니다.  
  
 이 단원에는 다음 항목이 포함되어 있습니다.  
  
 [방법: 지정 된 특성 또는 이름 (Visual Basic)를 사용 하 여 파일에 대 한 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 하나 이상의 속성을 검사 하 여 파일을 검색 하는 방법을 보여 줍니다. 그 <xref:System.IO.FileInfo>개체.</xref:System.IO.FileInfo>  
  
 [방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 그룹을 반환 하는 방법을 보여 줍니다 <xref:System.IO.FileInfo>파일 이름 확장명을 기반으로 하는 개체입니다.</xref:System.IO.FileInfo>  
  
 [방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 지정 된 디렉터리 트리에 있는 모든 파일의 총 바이트 수를 반환 하는 방법을 보여 줍니다.  
  
 [방법: 두 폴더 (Visual Basic) (LINQ)의 내용을 비교](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s  
 두 개의 지정 된 폴더에 있는 모든 파일 및 또한 모든 파일에 특정 폴더에만 다른 있는 반환 하는 방법을 보여 줍니다.  
  
 [방법: 파일 또는 디렉터리 트리 (LINQ) (Visual Basic)에서 파일에 대 한 가장 큰 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 디렉터리 트리에서 가장 크거나 작은 파일 또는 파일의 지정 된 수를 반환 하는 방법을 보여 줍니다.  
  
 [방법: 디렉터리 트리 (LINQ) (Visual Basic)에서 중복 파일 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 지정 된 디렉터리 트리에서 둘 이상의 위치에서 발생 하는 모든 파일 이름에 대 한 그룹화 하는 방법을 보여 줍니다. 또한 사용자 지정 비교자에 따라 좀 더 복잡 한 비교를 수행 하는 방법을 보여 줍니다.  
  
 [방법: 폴더 (Visual Basic) (LINQ)의 파일 내용 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 폴더 트리를 반복 하 고, 각 파일을 열고, 파일의 내용을 쿼리 하는 방법을 보여 줍니다.  
  
## <a name="comments"></a>설명  
 정확 하 게 파일 시스템의 내용을 나타내는 및 예외를 정상적으로 처리 하는 데이터 소스 만들기와 관련 된 몇 가지 복잡성이 있습니다. 이 섹션의 예에서는 스냅숏 컬렉션을 만들 <xref:System.IO.FileInfo>지정한 루트 폴더에 있는 모든 파일 및 모든 하위 폴더를 나타내는 개체입니다.</xref:System.IO.FileInfo> 각각의 실제 상태 <xref:System.IO.FileInfo>시작 하 고 쿼리 실행을 종료 하는 때 사이의 시간에 변경 될 수 있습니다.</xref:System.IO.FileInfo> 예를 들어 목록을 만들 수 있습니다 <xref:System.IO.FileInfo>데이터 원본으로 사용할 개체입니다.</xref:System.IO.FileInfo> 액세스 하려는 경우는 `Length` 쿼리에 있는 속성은 <xref:System.IO.FileInfo>개체의 값을 업데이트 하려면 파일 시스템에 액세스 하려고 합니다 `Length`.</xref:System.IO.FileInfo> 파일이 더 이상 존재 하는 경우는 <xref:System.IO.FileNotFoundException>쿼리에 쿼리하지 않는 경우 파일 시스템 직접.</xref:System.IO.FileNotFoundException> 이 섹션에서는 일부 쿼리는 특정 한 경우에 이러한 특정 예외를 사용 하는 별도 메서드를 사용 합니다. 또 다른 옵션은 <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher> 를 사용 하 여 동적으로 업데이트할 데이터 원본을 변경 하지 않으려면  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
