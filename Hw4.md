import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            Text("占卜APP").font(.largeTitle).fontWeight(.heavy).foregroundStyle(.primary).frame(width: 300, height: 60, alignment: .center).background(Color.cyan).cornerRadius(20)
            TabView{
                Group{
                }.toolbarBackground(Color.black, for: .tabBar).toolbarBackground(.visible, for: .tabBar)
                WelcomeView().tabItem{
                    Image(systemName: "house")
                    Text("Home")
                }
                CourseListView().tabItem{
                    Image(systemName: "list.bullet.clipboard.fill")
                    Text("Content")
                }
                CardView().tabItem{Image(systemName: "play.fill")
                    Text("Start")
                } 
            }.tint(.cyan)
        }
    }
    
    struct WelcomeView: View{
        var body: some View {
            VStack {
                Image("Octopus").resizable().aspectRatio( contentMode: .fit)
                Image(systemName: "bubble.left").rotationEffect(.degrees(180), anchor: .center).font(.system(size:180)).overlay(
                    Text("\n哈囉\n我來為您占卜").fontWeight(.heavy)).foregroundColor(.cyan)
            }
        }
    }
    
    
}

struct Course:Identifiable{
    var id=UUID()
    var name:String
    var image:String
    var description:String
}

var courses=[
    Course(name:"星座占卜",image:"P1",description: "星座運勢分析"),
    Course(name:"塔羅占卜",image:"P2",description: "塔羅牌算命"),
    Course(name:"紫微斗數",image:"P3",description: "命盤算命"),
    Course(name:"測字占卜",image:"P4",description: "輸入漢字算命"),
    Course(name:"抽籤占卜",image:"P5",description: "店長推薦")
]

struct BasicImageRow:View{
    var thisCourse:Course
    var body: some View{
        HStack{
            Image(thisCourse.image).resizable().frame(width: 40, height: 40).cornerRadius(5)
            Text(thisCourse.name)
        }
    }
}

struct CourseDetailView: View{
    @Environment(\.presentationMode) var presentationMode
    var thisCourse:Course
    var body: some View{
        ScrollView{
            VStack{
                Image(thisCourse.image).resizable().aspectRatio(contentMode: .fill).clipped()
                Text(thisCourse.description).font(.system(.subheadline, design: .rounded)).fontWeight(.light)
                Spacer()
            }
        } .overlay(
            HStack{
                Spacer()
                VStack{
                    Button(action: {self.presentationMode.wrappedValue.dismiss()}, label: { Image(systemName: "chevron.down.circle.fill").font(.largeTitle).foregroundColor(.white)
                    })
                    .padding(.trailing,20).padding(.top,40)
                    Spacer()
                }
            }
        )
    }
}
@State var showDetailView = false
@State var selectedCourse:Course?
struct CourseListView: View{
    var body: some View{
        NavigationView{
            List(courses){ courseItem in BasicImageRow(thisCourse: courseItem).onTapGesture {
                self.showDetailView = true
                self.selectedCourse = courseItem
            }
            }.sheet(item: self.$selectedCourse){ thisCourse in CourseDetailView(thisCourse: thisCourse)
            }.navigationBarTitle("占卜列表")
        }
    }
}

struct ContentView: View{
    @State var count : Int=0
    var body: some View{
        VStack{
            //Text(String(count)).padding(.all,10).frame(width: 150, height: 120, alignment: .center).font(.system(size: 100))
            if(count==0){
                Text("大吉").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else if(count==1){
                Text("中吉").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else if(count==2){
                Text("小吉").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else if(count==3){
                Text("吉").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else if(count==4){
                Text("兇").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else if(count==5){
                Text("小兇").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else if(count==6){
                Text("大兇").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            else{
                Text("我也不曉得").fontWeight(.heavy).lineSpacing(5)
                    .font(.system(size:100))
            }
            Button(action: {
                count = Int.random(in: 0...7)
                
            }, 
                   label: {
                Text("抽籤").padding(.all,10).frame(width: 200, height: 100, alignment: .center).font(.system(size: 30)).background(Color.purple).foregroundColor(.white).border(Color.purple, width: 5).cornerRadius(20)
            })
        }
    }
}
