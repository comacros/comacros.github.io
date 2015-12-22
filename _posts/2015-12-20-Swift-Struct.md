## Swift Struct

### Member/Static Constant/Variable

{% highlight swift %}
struct Contact {
    let firstName: String = "First"
    let lastName: String = "Last"
    static let UnitedStatesPhonePrefix = "+1"
}
	
let contact = Contact()
print(contact)		// "Contact(firstName: "First", lastName: "Last")\n"
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
