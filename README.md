# MARKRangeSlider

[![Version](https://img.shields.io/cocoapods/v/MARKRangeSlider.svg?style=flat)](http://cocoadocs.org/docsets/MARKRangeSlider)
[![License](https://img.shields.io/cocoapods/l/MARKRangeSlider.svg?style=flat)](http://cocoadocs.org/docsets/MARKRangeSlider)
[![Platform](https://img.shields.io/cocoapods/p/MARKRangeSlider.svg?style=flat)](http://cocoadocs.org/docsets/MARKRangeSlider)

A custom reusable slider control with 2 thumbs (range slider). Values range is between `minimumValue` and `maximumValue` (from 0 to 1 by default). The left thumb isn't able to go on the right side of the right thumb, and vice versa. Control enables multitouch (to use 2 fingers at 2 thumbs at the same time).

Please check Demo project for a basic example on how to use MARKRangeSlider.

### Available control properties
- `minimumValue` - the minimum value of the slider's range
- `maximumValue` - the maximum value of the slider's range
- `leftValue` - the value of the left thumb
- `rightValue` - the value of the right thumb
- `minimumDistance` - the distance between 2 thumbs (thumbs can't be closer to each other than this distance)

## Available styling properties
Images are customizable, default ones are used when no image is provided.
- `trackImage` - track background image
- `rangeImage` - range background image
- `leftThumbImage` - left thumb image
- `rightThumbImage` - right thumb image

## Usage

#### In your View Controller
```objc
- (void)viewDidLoad
{
    // ...
    self.rangeSlider = [[MARKRangeSlider alloc] initWithFrame:CGRectZero];
    [self.rangeSlider addTarget:self
                         action:@selector(rangeSliderValueDidChange:)
               forControlEvents:UIControlEventValueChanged];
    self.rangeSlider.minimumValue = 0.0;
    self.rangeSlider.maximumValue = 1.0;
    self.rangeSlider.leftValue = 0.2;
    self.rangeSlider.rightValue = 0.7;
    self.rangeSlider.minimumDistance = 0.2;

    [self.view addSubview:self.rangeSlider];
    // ...
}

- (void)rangeSliderValueDidChange:(MARKRangeSlider *)slider
{
    NSLog(@"%0.2f - %0.2f", slider.leftValue, slider.rightValue);
}

```

## Installation

**MARKRangeSlider** is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

`pod 'MARKRangeSlider'`

## Author

Vadym Markov, impressionwave@gmail.com

## License

**MARKRangeSlider** is available under the MIT license. See the LICENSE file for more info.
