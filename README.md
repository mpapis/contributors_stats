# Contributors stats

[![Build Status](https://travis-ci.org/mpapis/contributors_stats.png?branch=master)](https://travis-ci.org/mpapis/contributors_stats)
[![Code Climate](https://codeclimate.com/github/mpapis/contributors_stats.png)](https://codeclimate.com/github/mpapis/contributors_stats)
[![Dependency Status](https://gemnasium.com/mpapis/contributors_stats.png)](https://gemnasium.com/mpapis/contributors_stats)

Update static files with contributors statistics.

* Static content update of contributors statistics.
* Plugable backends to load data

## Example

```ruby
ContributorsStats.load(gh_org:  'railsisntaller').format(:markdown).save('public/contributors.md')
ContributorsStats.load(gh_repo: 'railsisntaller/website').format.update('public/index.html')
```

```shell
ruby -I lib:lib/plugins -rcontributors_stats -e "puts ContributorsStats.load(:gh_org => 'rvm', :gh_repo => ['wayneeseguin/rvm', 'wayneeseguin/rvm-capistrano'], :user_data => :fetch).format(:html).content"
```
