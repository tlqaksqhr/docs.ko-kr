---
title: '방법: Visual Basic에서 이진 파일에 쓰기'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 59edf84c1addd287eb1d1615c46258f329b1c7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587204"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>방법: Visual Basic에서 이진 파일에 쓰기
<xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> 메서드는 이진 파일에 데이터를 씁니다. `append` 매개 변수가 `True`이면 파일에 데이터를 추가합니다. 그렇지 않으면 파일의 데이터를 덮어씁니다.  
  
 파일 이름을 제외한 지정된 경로가 잘못된 경우 <xref:System.IO.DirectoryNotFoundException> 예외가 throw됩니다. 경로가 유효하지만 파일이 없는 경우 파일이 생성됩니다.  
  
### <a name="to-write-to-a-binary-file"></a>이진 파일에 쓰려면  
  
-   파일 경로 및 이름과 쓸 바이트를 제공하여 `WriteAllBytes` 메서드를 사용합니다. 이 예제에서는 `CollectedData.dat`라는 파일에 데이터 배열 `CustomerData`를 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서는 예외가 생성될 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백으로만 구성되거나, 잘못된 문자를 포함하는 경우 등의 이유로 경로가 유효하지 않은 경우 (<xref:System.ArgumentException>).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)  
  
-   `File`이 존재하지 않는 경로를 가리키는 경우(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>)  
  
-   다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>  
 [방법: 파일에 텍스트 쓰기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
