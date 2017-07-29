---
title: "방법: Visual Basic에서 특정 패턴의 파일 찾기"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e5d7dc692bf68ebccc459e9cf3f92c3683b8145
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a>방법: Visual Basic에서 특정 패턴의 파일 찾기
<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> 메서드는 파일의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다. `wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다. 하위 디렉터리를 검색에 포함하려면 `searchType` 매개 변수를 `SearchOption.SearchAllSubDirectories`로 설정합니다.  
  
 지정한 패턴과 일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.  
  
> [!NOTE]
>  `System.IO` 네임스페이스의 `DirectoryInfo` 클래스를 사용하여 파일 목록을 반환하는 방법에 대한 자세한 내용은 <xref:System.IO.DirectoryInfo.GetFiles%2A>를 참조하세요.  
  
### <a name="to-find-files-with-a-specified-pattern"></a>지정된 패턴의 파일을 찾으려면  
  
-   검색하려는 디렉터리의 이름 및 경로를 제공하고 패턴을 지정하여 `GetFiles` 메서드를 사용합니다. 다음 예제에서는 디렉터리에서 `.dll` 확장명을 가진 모든 파일을 반환하고 `ListBox1`에 추가합니다.  
  
     [!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 다음 조건에서 예외가 발생합니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)  
  
-   `directory`가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)  
  
-   `directory`가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)  
  
-   경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)  
  
-   사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [방법: 특정 패턴의 하위 디렉터리 찾기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [문제 해결: 텍스트 파일 읽기 및 쓰기](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [방법: 디렉터리의 파일 컬렉션 가져오기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

