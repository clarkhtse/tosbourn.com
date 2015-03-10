---
layout: post
status: publish
published: true
title: Some stumbling blocks I hit following my first Swift tutorial
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 2492
wordpress_url: http://tosbourn.com/?p=2492
date: '2015-01-19 20:57:11 +0000'
date_gmt: '2015-01-19 19:57:11 +0000'
categories:
- Development Help
tags:
- xCode
- '365'
- Swift
comments: []
---
<p>I am trying to pick up some Swift to help me with a project I want to work on so I figured I would dive in with a basic tutorial to get my feet wet in the language and remember what Xcode looks like.</p>
<p>I decided to follow <a href="http://ios-blog.co.uk/tutorials/developing-ios-apps-using-swift-part-1/">this tutorial</a> – the purpose of which was to build a really basic table that would get data in from your controller.</p>
<p>Even though the tutorial covered everything you needed to get by, there have been a few changes to how Swift works since it was written and also a few things they take for granted (like you knowing where certain views are inside of Xcode).</p>
<p>The first two stumbling block I hit was that once I opened a storyboard file I didn't know how to open the object library. When I searched for it the screenshots I found were from older versions of Xcode.</p>
<p>[caption id="attachment_2493" align="aligncenter" width="540"]<a href="http://tosbourn.com/wp-content/uploads/2015/01/Screenshot-2015-01-19-19.09.46.png"><img class="size-full wp-image-2493" src="http://tosbourn.com/wp-content/uploads/2015/01/Screenshot-2015-01-19-19.09.46.png" alt="The blue icon showing that the object library has been selected in Xcode" width="540" height="274" /></a> The blue icon showing that the object library has been selected in Xcode[/caption]</p>
<p>The next problem I faced was that once I had my table inside of my view I was told;</p>
<blockquote><p>Now we need to set up a delegate and data source for the table view. This is easy to do in interface builder. Just hold control, and then click and drag from the tableview to the “View Controller” object in your storyboard’s hierarchy, and select ‘data source’. Repeat with the ‘delegate’ options.</p></blockquote>
<p>I could not find this storyboard hierarchy to save my life! Some more searching and I found what I needed, for reference it is this little black icon.</p>
<p>[caption id="attachment_2494" align="aligncenter" width="482"]<a href="http://tosbourn.com/wp-content/uploads/2015/01/Screenshot-2015-01-19-19.12.49.png"><img class="size-full wp-image-2494" src="http://tosbourn.com/wp-content/uploads/2015/01/Screenshot-2015-01-19-19.12.49.png" alt="Icon to see the storyboard hierarchy" width="482" height="180" /></a> Icon to see the storyboard hierarchy[/caption]</p>
<p>Now with my Xcode woes out of the way I was able to down to actually typing some code (as a vim user all this clicking and dragging was very disturbing!)</p>
<p>The code we were expected to have in our completed viewController file was;</p>
<pre><code>import UIKit

class ViewController: UIViewController, UITableViewDataSource, UITableViewDelegate {

override func viewDidLoad() {
super.viewDidLoad()
// Do any additional setup after loading the view, typically from a nib.
}

override func didReceiveMemoryWarning() {
super.didReceiveMemoryWarning()
// Dispose of any resources that can be recreated.
}

func tableView(tableView: UITableView!, numberOfRowsInSection section: Int) -&gt; Int {
return 10
}


func tableView(tableView: UITableView!, cellForRowAtIndexPath indexPath: NSIndexPath!) -&gt; UITableViewCell! {
let cell: UITableViewCell = UITableViewCell(style: UITableViewCellStyle.Subtitle, reuseIdentifier: "MyTestCell")

cell.text = "Row #\(indexPath.row)"
cell.detailTextLabel.text = "Subtitle #\(indexPath.row)"

return cell
}


}</code></pre>
<p>There are a few issues with this. The first is that you will see in our two tableView functions we are appending ! to several parameters.</p>
<p>The interface around this has changed so you need to remove these bangs.</p>
<p>The second issue is that UITableViewCell now has what is known as <a href="https://developer.apple.com/library/mac/documentation/Swift/Conceptual/Swift_Programming_Language/OptionalChaining.html">optional chaining</a>. When querying properties that are known to possibly return nil they should be asked for with a question mark.</p>
<p>Finally, you cannot just call .text on a UITableViewCell anymore, you need to go through textLabel? first.</p>
<p>This makes my completed and working code for those two functions to be;</p>
<pre><code>
    func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -&gt; Int {
        return 10
    }
    
    func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -&gt; UITableViewCell {
        let cell: UITableViewCell = UITableViewCell(style: UITableViewCellStyle.Subtitle, reuseIdentifier: "MyTestCell")
        
        cell.textLabel?.text = "Row #\(indexPath.row)"
        cell.detailTextLabel?.text = "Subtitle #\(indexPath.row)"
        
        return cell
    }
</code></pre>
<p>I really hope this helps other people that are struggling to work with very useful but slightly out of date tutorials.</p>
<p>I have uploaded my finished project to Github if you want to have a look. The main file that I was editing is the <a href="https://github.com/tosbourn/following-swift-tutorial/blob/master/Learning%20Swift/ViewController.swift">viewController</a>.</p>
