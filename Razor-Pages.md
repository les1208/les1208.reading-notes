### Intro to Razor pages
- Razor Pages is a new aspect of ASP.NET Core MVC that makes coding page-focused scenarios easier and more productive.
	- Razor Pages is enabled in Startup.cs:

	###  Write basicforms
	-Razor Pages is designed to make common patterns used with web browsers easy to implement when building an app. Model binding, Tag Helpers, and HTML helpers all just work with the properties defined in a Razor Page class. Consider a page that implements a basic "contact us" form for the Contact model:

#### Razor Pages Application Structure
- ASP.NET Core: Razor Pages projectApplication structure is similar to MVC but there are no folders for controllers and views. The folder called Pages contains all Razor views that in this context are called “pages”. These pages are like regular MVC views but they also contain code that for MVC is held in controller classes. I will cover this part of Razor Pages later.
- Program and Startup classes are exactly the same as for MVC applications. Not just by name but also by code. As said before, Razor Pages are supported by MVC and they are part of it.
- Pages are always marked with @page directive that tells view engine this is Razor page and not a regular MVC view. We can specify model that is acting more like a view model than regular MVC model. Actually model here is more like mix of controller and model. Those who have used XAML should find it familiar by concept. 
