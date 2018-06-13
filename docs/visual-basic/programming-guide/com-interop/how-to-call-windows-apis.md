---
title: '방법: Windows API 호출(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: de568c3273d4d040c6566136e5d59e2155b86f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643642"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>방법: Windows API 호출(Visual Basic)
정의 하 고 호출 하는이 예제는 `MessageBox` user32.dll의 함수에는 문자열을 전달 합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System> 네임스페이스에 대한 참조  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   메서드가 정적이 아니거나,는 추상 클래스 또는 이전에 정의 된 합니다. 부모 형식이 인터페이스 또는 길이의 *이름* 또는 *dllName* 은 0입니다. (<xref:System.ArgumentException>)  
  
-   *이름* 또는 *dllName* 은 `Nothing`합니다. (<xref:System.ArgumentNullException>)  
  
-   포함하는 형식은 `CreateType`을 사용하여 이전에 만든 것입니다. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>참고 항목  
 [플랫폼 호출 자세히 보기](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [플랫폼 호출 예제](../../../framework/interop/platform-invoke-examples.md)  
 [관리되지 않는 DLL 함수 사용](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [내보내기를 리플렉션 사용 하 여 메서드를 정의 합니다.](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)
