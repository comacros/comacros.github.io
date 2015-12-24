---
layout: post
title: Swift Struct
---

## Swift Struct

### Member/Static Constant/Variable

{% highlight swift %}
struct Contact {
    let firstName: String = "First"
    let lastName: String = "Last"
    static let UnitedStatesPhonePrefix = "+1"
}
	
let contact = Contact()
print(contact)	// "Contact(firstName: "First", lastName: "Last")\n"
print(Contact.UnitedStatesPhonePrefix)	// "+1\n"
print(contact.UnitedStatesPhonePrefix)	// Error: Static member cannot be used on instance
{% endhighlight %}

### Computed Properties

{% highlight swift %}
struct Ball {
    var radius: Double
    var diameter: Double {
        get {
            return self.radius * 2
        }
        set {
            self.radius = newValue / 2.0
        }
    }
}
{% endhighlight %}
	
### Property Observers

{% highlight swift %}
struct StepCounter {
    var totalSteps: Int = 0 {
        willSet {
            print("to be: \(newValue)")
        }
        didSet {
            print("used to be: \(oldValue)")
        }
    }
}

var stepCounter = StepCounter()
stepCounter.totalSteps = 100
// to be: 100
// used to be: 0
{% endhighlight %}

### Subscripts

{% highlight swift %}
struct MovieAssignment {
    var movies: [String:String]
    subscript(invitee: String) -> String? {
        get {
            return self.movies[invitee]
        }
        set {
            self.movies[invitee] = newValue
        }
    }
}
	
var assignment = MovieAssignment(movies: [:])
assignment["Sarah"] = "Modern Family"
print(assignment["Sarah"])	// Optional("Modern Family")
{% endhighlight %}
	
### Custom Initialization
Every member variable and constant must have a value by the end of the initializer.

{% highlight swift %}
struct Address {
    var city: String
    var province: String
    var country: String = "P.R.China"

    init(city: String, province: String) {
        self.city = city
        self.province = province
    }

    init(city: String, province: String, country: String) {
        self.city = city
        self.province = province
        self.country = country
    }
}

var guangzhou = Address(city: "Guangzhou", province: "Guangdong")
{% endhighlight %}
