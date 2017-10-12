# YHInfiniteScrollView

[![CI Status](http://img.shields.io/travis/yonghwinam/YHInfiniteScrollView.svg?style=flat)](https://travis-ci.org/yonghwinam/YHInfiniteScrollView)
[![Version](https://img.shields.io/cocoapods/v/YHInfiniteScrollView.svg?style=flat)](http://cocoapods.org/pods/YHInfiniteScrollView)
[![License](https://img.shields.io/cocoapods/l/YHInfiniteScrollView.svg?style=flat)](http://cocoapods.org/pods/YHInfiniteScrollView)
[![Platform](https://img.shields.io/cocoapods/p/YHInfiniteScrollView.svg?style=flat)](http://cocoapods.org/pods/YHInfiniteScrollView)

## Preview

![](Example/YHInfiniteScrollView/demo.gif)



## Installation

YHInfiniteScrollView is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'YHInfiniteScrollView'
```

## Usage

```
import UIKit
import YHInfiniteScrollView


override func viewDidLoad() {
super.viewDidLoad()

// Create content view controllers or views
let firstViewContorller = self.storyboard?.instantiateViewController(withIdentifier: "FirstViewController")
let secondViewController = self.storyboard?.instantiateViewController(withIdentifier: "SecondViewController")
let thirdViewController = self.storyboard?.instantiateViewController(withIdentifier: "ThirdViewController")
let fourthViewController = self.storyboard?.instantiateViewController(withIdentifier: "FourthViewController")
let fifthViewController = self.storyboard?.instantiateViewController(withIdentifier: "FifthViewController")

self.addChildViewController(firstViewContorller!)
self.addChildViewController(secondViewController!)
self.addChildViewController(thirdViewController!)
self.addChildViewController(fourthViewController!)
self.addChildViewController(fifthViewController!)

// Initialize infinite scroll view with contents
let infiniteScrollView = YHInfiniteScrollView.init(frame: CGRect.zero,
contentObjects: [firstViewContorller!, secondViewController!, thirdViewController!, fourthViewController!, fifthViewController! ])
infiniteScrollView.translatesAutoresizingMaskIntoConstraints = false
infiniteScrollView.delegate = self

// Add infinite scroll view to container view (assume that existing container view)
self.mainContainer.addSubview(infiniteScrollView)

// Add layuout contraints
let alcTop = NSLayoutConstraint.init(item: infiniteScrollView, attribute: .top, relatedBy: .equal, toItem: self.mainContainer, attribute: .top, multiplier: 1.0, constant: 0.0)
let alcLeading = NSLayoutConstraint.init(item: infiniteScrollView, attribute: .leading, relatedBy: .equal, toItem: self.mainContainer, attribute: .leading, multiplier: 1.0, constant: 0.0)
let alcBottom = NSLayoutConstraint.init(item: infiniteScrollView, attribute: .bottom, relatedBy: .equal, toItem: self.mainContainer, attribute: .bottom, multiplier: 1.0, constant: 0.0)
let alcTrailing = NSLayoutConstraint.init(item: infiniteScrollView, attribute: .trailing, relatedBy: .equal, toItem: self.mainContainer, attribute: .trailing, multiplier: 1.0, constant: 0.0)

self.mainContainer.addConstraints([alcTop, alcLeading, alcBottom, alcTrailing])
}

```

## Author

Yonghwi (yonghwi.nam@gmail.com)

## License

YHInfiniteScrollView is available under the MIT license. See the LICENSE file for more info.
