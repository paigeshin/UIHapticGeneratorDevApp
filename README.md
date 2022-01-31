```swift

//
//  ContentView.swift
//  Feedback Impact
//
//  Created by paige on 2022/01/31.
//

import SwiftUI

struct ContentView: View {
    var body: some View {
        NavigationView {
            VStack {
                VStack {
                    Text("Notification")
                    HStack {
                        Button {
                            HapticHelper.notification(type: .success)
                        } label: {
                            Text("Success")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                        Button {
                            HapticHelper.notification(type: .warning)
                        } label: {
                            Text("Warning")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                        Button {
                            HapticHelper.notification(type: .error)
                        } label: {
                            Text("Error")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                    }

                }

                VStack {
                    Text("impact")
                    HStack {
                        Button {
                            HapticHelper.impact(style: .rigid)
                        } label: {
                            Text("Rigid")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                        Button {
                            HapticHelper.impact(style: .heavy)
                        } label: {
                            Text("Heavy")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                        Button {
                            HapticHelper.impact(style: .medium)
                        } label: {
                            Text("Medium")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }
                    }
                    HStack {
                        Button {
                            HapticHelper.impact(style: .medium)
                        } label: {
                            Text("Meidum")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                        Button {
                            HapticHelper.impact(style: .light)
                        } label: {
                            Text("Light")
                                .foregroundColor(.white)
                                .padding()
                                .background(.blue)
                                .clipShape(Capsule())
                        }

                    }
                }

            }
            .navigationTitle("UI FEEDBACK")
        }


    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}


struct HapticHelper {

    // warning, error, success
    static func notification(type: UINotificationFeedbackGenerator.FeedbackType) {
        let generator: UINotificationFeedbackGenerator = UINotificationFeedbackGenerator()
        generator.notificationOccurred(type)
    }

    // heavy,light, medium, rigid, soft
    static func impact(style: UIImpactFeedbackGenerator.FeedbackStyle) {
        let generator: UIImpactFeedbackGenerator = UIImpactFeedbackGenerator(style: style)
        generator.impactOccurred()
    }

}


```
