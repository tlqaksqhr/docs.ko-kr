---
title: 레지스트리 읽기 및 쓰기(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 6ce05b956ebf9a544eb8c95165b0f709c694f334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584620"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>레지스트리 읽기 및 쓰기(Visual Basic)
이 항목에서는 레지스트리와 관련된 작업 및 개념 항목에 대해 설명합니다.  
  
 Visual Basic에서 프로그래밍할 때 Visual Basic에서 제공하는 기능 또는 .NET Framework의 레지스트리 클래스를 사용하여 레지스트리에 액세스하도록 선택할 수 있습니다. 레지스트리는 운영 체제의 정보는 물론 컴퓨터에 호스트된 응용 프로그램의 정보도 호스트합니다. 레지스트리로 작업하면 시스템 리소스나 보호된 정보에 부적절하게 액세스하여 보안이 손상될 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 레지스트리 키 만들기 및 값 설정](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 `My.Computer.Registry` 개체의 `CreateSubKey` 및 `SetValue` 메서드를 사용하여 레지스트리 키를 만들고 값을 설정하는 방법을 설명합니다.  
  
 [방법: 레지스트리 키 값 읽기](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 `My.Computer.Registry` 개체의 `GetValue` 메서드를 사용하여 레지스트리 키에서 값을 읽는 방법을 설명합니다.  
  
 [방법: 레지스트리 키 삭제](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 `My.Computer.Registry.CurrentUser` 속성의 `DeleteSubKey` 메서드를 사용하여 레지스트리 키를 삭제하는 방법을 설명합니다.  
  
 [Microsoft.Win32 네임스페이스를 사용하여 레지스트리 읽기 및 쓰기](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 `Registry` 및 `RegistryKey` 클래스를 사용하여 레지스트리에 액세스하는 방법을 설명합니다.  
  
 [보안 및 레지스트리](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 레지스트리 관련 보안 문제를 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 `My.Computer.Registry` 개체의 멤버를 나열하고 설명합니다.  
  
 <xref:Microsoft.Win32.Registry>  
 개별 키와 멤버에 대한 링크와 함께 `Registry` 클래스의 개요를 제공합니다.
