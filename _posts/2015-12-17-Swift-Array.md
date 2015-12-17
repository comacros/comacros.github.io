---
layout: post
title: Swift Array
---

### Initializers

{% highlight swift %}

var xs = [Int]()
	
var xs = [1, 2, 3]
var xs: [Int] = [1, 2, 3]
	
var xs = [Int](count: 3, repeatedValue: 1)		// [1, 1, 1]
var xs = [Int](arrayLiteral: 1, 2, 3)			// [1, 2, 3]

{% endhighlight %}

### Instance Variable

{% highlight swift %}

// var xs = [1, 2, 3]
xs.startIndex			// 0
xs.endIndex			// 3, "past-the-end" element index
xs.count			// 3
xs.capacity			// Number of elements without reallocation

{% endhighlight %}

### Instance Methods

{% highlight swift %}
// var xs = [1]
xs.reserveCapacity(10)				// xs.capacity = 10

xs.append(2)					// [1, 2]
xs.appendContentsOf([3])			// [1, 2, 3]
xs.appendContentsOf(Set<Int>(arrayLiteral: 4))	// [1, 2, 3, 4]
xs += [5]					// [1, 2, 3, 4, 5]

xs.removeLast()					// [1, 2, 3, 4], returns 5
xs.popLast()					// [1, 2, 3], returns Optional(4)
xs.removeAtIndex(2)				// [1, 2], returns 3

xs.insert(0, atIndex: 0)			// [0, 1, 2]
xs.insertContentsOf([3], at: 3)			// [0, 1, 2, 3]

xs.replaceRange(1...2, with: [2, 1])		// [0, 2, 1, 3]
xs[1...2] = [1, 2]				// [0, 1, 2, 3]
xs[1...3] = []					// [0]
xs[0...0] = [1, 2]				// [1, 2]

{% endhighlight %}
