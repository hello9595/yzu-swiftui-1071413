<h1>HW1</h1>
    
```swift

import SwiftUI

struct ContentView: View {
    var body: some View{
        Image("Picture_me").resizable().aspectRatio(contentMode: .fill )
            .rotationEffect(.degrees(180), anchor: .center)
            .overlay(
                Text("英國研究指出：\n在印度,\n每60秒就有一分鐘經過.")
                    .fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:24)).foregroundColor(.white).frame(width: 350, height: 150, alignment: .center )
                    .background(Color.black).cornerRadius(30).opacity(0.8),
                alignment: .bottom
            )
            .overlay(
                Text("1071413\n陳濰榛")
                  .font(.system(size:50))
                  .fontWeight(.bold)
                    .position(x: 400, y:400)
                    .shadow(color: .black, radius: 10)
            )
            .overlay(
                Image(systemName: "timer")
                    .font(.system(size:150)).foregroundColor(/*@START_MENU_TOKEN@*/.blue/*@END_MENU_TOKEN@*/).shadow(color: .black, radius: 10, x: 5, y: 1)
                    .position(x: 550, y:450)
            )
    }
}

```

<img width="25%"  src="https://raw.githubusercontent.com/hello9595/yzu-swiftui-1071413/main/hw1_screenshot.jpg?token=GHSAT0AAAAAACJW3YXIDWIBYHZALOCEPIK4ZKCDRGQ">
