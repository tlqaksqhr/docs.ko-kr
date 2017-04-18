---
title: "WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정
WPF\(Windows Presentation Foundation\)는 Windows 7 터치 입력 처리를 기본적으로 지원합니다. 지원은 <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A> 및 <xref:System.Windows.UIElement.OnStylusMove%2A> 이벤트와 같은 태블릿 플랫폼의 실시간 스타일러스 입력을 통해 제공됩니다.  또한 Windows 7에서는 다중 터치 입력을 Win32 WM\_TOUCH 창 메시지로 제공합니다.  이 두 API는 동일한 HWND에서 함께 사용할 수 없습니다.  태블릿 플랫폼\(WPF 응용 프로그램의 기본값\)을 통해 터치 입력을 사용할 경우 WM\_TOUCH 메시지를 사용할 수 없습니다.  따라서 WM\_TOUCH를 사용하여 WPF 창에서 터치 메시지를 받으려면 WPF에서 기본 제공 스타일러스 지원을 해제해야 합니다.  이는 WM\_TOUCH를 사용하는 구성 요소를 호스팅하는 WPF 창과 같은 시나리오에서 적용될 수 있습니다.  
  
 WPF의 스타일러스 입력 수신을 해제하려면 WPF 창에 추가된 태블릿 지원을 제거합니다.  
  
## 예제  
 다음 샘플 코드에서는 리플렉션을 사용하여 기본 태블릿 플랫폼 지원을 제거하는 방법을 보여 줍니다.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## 참고 항목  
 [스타일러스에서 입력 가로채기](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)