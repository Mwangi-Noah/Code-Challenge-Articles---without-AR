# Code-Challenge-Articles---without-AR
In this code Challenge, we have three models: Author, Article, and Magazine. Our model for the file is as follows:

User
├── Gemfile
├── Gemfile.lock
├── README.md
├── bin
│   └── run
├── config
│   └── environment.rb
├── lib
│   ├── author.rb
│   ├── magazine.rb
│   └── article.rb

# .Author
in the author class, we have several instance methods that include #initialize, whose task is to intialize a new instance of the author when run. the #articles method returns an array of Article instances the author has written. Here, we introduce the self keyword that points to that specific instance of the author. The #magazine method returns an array of unique magazine instances the author has contributed to. Here, we introduce the .map method that is similar to the Javascript method in that it loops through the array of stored magazines. The .uniq method just returns magazines names that are not duplicated, i.e. if there was an error in input and the same name was provided multiple times.
# .Article
The .Article class was not as long as the aoouthor and only had few methods. The class variable  @@all is an array that will store all instances of Article created. The def self.all class method will return the @@all array containing all instances of Article. It allows accessing all the articles created. In summary, the Article class provides a way to create and store instances of articles with their associated author, magazine, and title. The self.all method enables retrieving all the articles that have been created.

# .Magazine
As in the Article class, The class variable  @@all is an array that will store all instances of magazine created. the def The def self.all class method will return the @@all array containing all instances of 'Magazine'. The 'def self.find_by_name(name)' class method takes a name parameter. It searches for a magazine in the @@all array that matches the given name and returns the first matching magazine object. The 'def article_titles' is an instance method that returns an array of titles for all articles associated with the current magazine. It uses the Article.all class method to access all articles and filters them based on the magazine match. It then maps the titles from the filtered articles. Finally, the "def contributing_authors" instance method returns an array of authors who have written more than two articles for the current magazine. It groups all articles by author using group_by, filters the groups to select authors with more than two articles (articles.size > 2), and returns the keys (authors) of the filtered groups.

