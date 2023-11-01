import SwiftUI

struct ContentView: View {
    var body: some View{
        Image("Picture_me").resizable().aspectRatio(contentMode: .fill )
            .rotationEffect(.degrees(180), anchor: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
            .overlay(
                Text("英國研究指出：\n在印度,\n每60秒就有一分鐘經過.")
                    .fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:24)).foregroundColor(.white).frame(width: 350, height: 150, alignment: .center )
                    .background(Color.black).cornerRadius(30).opacity(/*@START_MENU_TOKEN@*/0.8/*@END_MENU_TOKEN@*/),
                alignment: .bottom
            )
            .overlay(
                Text("1071413\n陳濰榛")
                  .font(.system(size:50))
                  .fontWeight(.bold)
                    .position(x: 400, y:400)
                    .shadow(color: /*@START_MENU_TOKEN@*/.black/*@END_MENU_TOKEN@*/, radius: 10)
            )
            .overlay(
                Image(systemName: "timer")
                    .font(.system(size:150)).foregroundColor(/*@START_MENU_TOKEN@*/.blue/*@END_MENU_TOKEN@*/).shadow(color: .black, radius: /*@START_MENU_TOKEN@*/10/*@END_MENU_TOKEN@*/, x: 5, y: 1)
                    .position(x: 550, y:450)
            )
    }
}

