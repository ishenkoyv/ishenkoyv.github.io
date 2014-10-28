Octofound is a Foundation-5 theme for Octopress. <strong><a href="http://annejohnson.github.io/octofound-demo">Click here for a demo.</a></strong>

<h3>Theme Features:</h3>

<ul>
	<li><strong>Completely responsive</strong>: adapts to any screen size, from ginormous to mobile.</li>
	<li><strong>All of Foundation 5's SASS and Javascript components</strong> are included. <a href="http://foundation.zurb.com/docs/sass.html">Browse Foundation's docs</a> to learn about what these components enable you to do.</li>
	<li><strong>SASS files</strong> that are highly documented and easy-to-edit: _settings.scss & screen.scss</li>
	<li><strong>No-sidebar, left-sidebar, and right-sidebar</strong> page templates. To use these different layouts, open <code>your_page_or_post.markdown</code> and add the line <code>sidebar: false</code> to hide the sidebar, or <code>sidebar_left: true</code> to make the sidebar display on the left. The sidebar displays on the right by default.</li>
	<li><strong>Sticky navigation bar:</strong> to make the navigation bar stick to the top of the page, add the line <code>fixed_navigation: true</code> to your <code>_config.yml</code> file.</li>
	<li><strong>Optional subtitles on pages:</strong> in <code>your_page.markdown</code>, put the line <code>subtitle: Your Subtitle Here</code> in the header to give that page a subtitle.</li>
	<li><strong>Font Awesome 4.0.3:</strong> <a href="http://fortawesome.github.io/Font-Awesome/icons/">click here</a> to browse the amazing icons at your fingertips.</li>
</ul>

<h3>Installation:</h3>
<ol>
	<li>Add the following lines to your config.rb file:
		<ul>
			<li><code>add_import_path "source/assets/bower_components/foundation/scss"</code>
			</li>
			<li><code>javascripts_dir = "source/js"</code></li>
		</ul>

	</li>
	<li>Install the theme using these commands:
		<ul>
			<li><code>$ cd your_octopress_root</code></li>
			<li><code>$ git clone https://github.com/annejohnson/octofound .themes/octofound</code></li>
			<li><code>$ rake install['octofound'] (or rake install\['octofound'\])</code></li>
			<li><code>$ rake generate</code></li>
		</ul>
	</li>
	<li>Customize site and update the navigation (in <strong>_includes/custom/navigation.html</strong>).
	</li>

</ol>
