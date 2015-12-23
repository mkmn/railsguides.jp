**DO NOT READ THIS FILE ON GITHUB, GUIDES ARE PUBLISHED ON http://guides.rubyonrails.org.**

Ruby on Rails 5.0 Release Notes
===============================

Highlights in Rails 5.0:

* Action Cable
* Rails API
* Active Record Attributes API
* Test Runner
* Exclusive use of `rails` CLI over Rake
* Sprockets 3
* Turbolinks 5
* Ruby 2.2.2+ required

These release notes cover only the major changes. To learn about various bug
fixes and changes, please refer to the change logs or check out the [list of
commits](https://github.com/rails/rails/commits/5-0-stable) in the main Rails
repository on GitHub.

--------------------------------------------------------------------------------

Upgrading to Rails 5.0
----------------------

If you're upgrading an existing application, it's a great idea to have good test
coverage before going in. You should also first upgrade to Rails 4.2 in case you
haven't and make sure your application still runs as expected before attempting
an update to Rails 5.0. A list of things to watch out for when upgrading is
available in the
[Upgrading Ruby on Rails](upgrading_ruby_on_rails.html#upgrading-from-rails-4-2-to-rails-5-0)
guide.


Major Features
--------------

### Action Cable
[Pull Request](https://github.com/rails/rails/pull/22586)

ToDo...

### Rails API
[Pull Request](https://github.com/rails/rails/pull/19832)

ToDo...

### Active Record attributes API

ToDo...

### Test Runner
[Pull Request](https://github.com/rails/rails/pull/19216)

ToDo...


Railties
--------

Please refer to the [Changelog][railties] for detailed changes.

### Removals

*   Removed debugger support, use byebug instead. `debugger` is not supported by
    Ruby
    2.2. ([commit](https://github.com/rails/rails/commit/93559da4826546d07014f8cfa399b64b4a143127))

*   Removed deprecated `test:all` and `test:all:db` tasks.
    ([commit](https://github.com/rails/rails/commit/f663132eef0e5d96bf2a58cec9f7c856db20be7c))

*   Removed deprecated `Rails::Rack::LogTailer`.
    ([commit](https://github.com/rails/rails/commit/c564dcb75c191ab3d21cc6f920998b0d6fbca623))

*   Removed deprecated `RAILS_CACHE` constant.
    ([commit](https://github.com/rails/rails/commit/b7f856ce488ef8f6bf4c12bb549f462cb7671c08))

*   Removed deprecated `serve_static_assets` configuration.
    ([commit](https://github.com/rails/rails/commit/463b5d7581ee16bfaddf34ca349b7d1b5878097c))

*   Removed the documentation tasks `doc:app`, `doc:rails`, and `doc:guides`.
    ([commit](https://github.com/rails/rails/commit/cd7cc5254b090ccbb84dcee4408a5acede25ef2a))

### Deprecations

*   Deprecated `config.static_cache_control` in favor of
    `config.public_file_server.headers`.
    ([Pull Request](https://github.com/rails/rails/pull/22173))

*   Deprecated `config.serve_static_files` in favor of `config.public_file_server.enabled`.
    ([Pull Request](https://github.com/rails/rails/pull/22173))

### Notable changes

*   Added Rails test runner `bin/rails test`.
    ([Pull Request](https://github.com/rails/rails/pull/19216))

*   Newly generated applications and plugins get a `README.md` in Markdown.
    ([commit](https://github.com/rails/rails/commit/89a12c931b1f00b90e74afffcdc2fc21f14ca663),
     [Pull Request](https://github.com/rails/rails/pull/22068))

*   Added `bin/rails restart` task to restart your Rails app by touching `tmp/restart.txt`.
    ([Pull Request](https://github.com/rails/rails/pull/18965))

*   Added `bin/rails initializers` task to print out all defined initializers in
    the order they are invoked by Rails.
    ([Pull Request](https://github.com/rails/rails/pull/19323))

*   Removed `Rack::ContentLength` middleware from the default
    stack. ([Commit](https://github.com/rails/rails/commit/56903585a099ab67a7acfaaef0a02db8fe80c450))

*   Added `bin/rails dev:cache` to enable or disable caching in development mode.
    ([Pull Request](https://github.com/rails/rails/pull/20961))

*   Added `bin/update` script to update the development environment automatically.
    ([Pull Request](https://github.com/rails/rails/pull/20972))

*   Proxy Rake tasks through `bin/rails`.
    ([Pull Request](https://github.com/rails/rails/pull/22457),
     [Pull Request](https://github.com/rails/rails/pull/22288))


Action Pack
-----------

Please refer to the [Changelog][action-pack] for detailed changes.

### Removals

*   Removed `ActionDispatch::Request::Utils.deep_munge`.
    ([commit](https://github.com/rails/rails/commit/52cf1a71b393486435fab4386a8663b146608996))

*   Removed `ActionController::HideActions`.
    ([Pull Request](https://github.com/rails/rails/pull/18371))

*   Removed `respond_to` and `respond_with` placeholder methods, this functionality
    has been extracted to the
    [responders](https://github.com/plataformatec/responders) gem.
    ([commit](https://github.com/rails/rails/commit/afd5e9a7ff0072e482b0b0e8e238d21b070b6280))

*   Removed deprecated assertion files.
    ([commit](https://github.com/rails/rails/commit/92e27d30d8112962ee068f7b14aa7b10daf0c976))

*   Removed deprecated usage of string keys in URL helpers.
    ([commit](https://github.com/rails/rails/commit/34e380764edede47f7ebe0c7671d6f9c9dc7e809))

*   Removed deprecated `only_path` option on `*_path` helpers.
    ([commit](https://github.com/rails/rails/commit/e4e1fd7ade47771067177254cb133564a3422b8a))

*   Removed deprecated `NamedRouteCollection#helpers`.
    ([commit](https://github.com/rails/rails/commit/2cc91c37bc2e32b7a04b2d782fb8f4a69a14503f))

*   Removed deprecated support to define routes with `:to` option that doesn't contain `#`.
    ([commit](https://github.com/rails/rails/commit/1f3b0a8609c00278b9a10076040ac9c90a9cc4a6))

*   Removed deprecated `ActionDispatch::Response#to_ary`.
    ([commit](https://github.com/rails/rails/commit/4b19d5b7bcdf4f11bd1e2e9ed2149a958e338c01))

*   Removed deprecated `ActionDispatch::Request#deep_munge`.
    ([commit](https://github.com/rails/rails/commit/7676659633057dacd97b8da66e0d9119809b343e))

*   Removed deprecated
    `ActionDispatch::Http::Parameters#symbolized_path_parameters`.
    ([commit](https://github.com/rails/rails/commit/7fe7973cd8bd119b724d72c5f617cf94c18edf9e))

*   Removed deprecated option `use_route` in controller tests.
    ([commit](https://github.com/rails/rails/commit/e4cfd353a47369dd32198b0e67b8cbb2f9a1c548))

*   Removed `assigns` and `assert_template`. Both methods have been extracted
    into the
    [rails-controller-testing](https://github.com/rails/rails-controller-testing)
    gem.
    ([Pull Request](https://github.com/rails/rails/pull/20138))

### Deprecations

*   Deprecated all `*_filter` callbacks in favor of `*_action` callbacks.
    ([Pull Request](https://github.com/rails/rails/pull/18410))

*   Deprecated `*_via_redirect` integration test methods. Use `follow_redirect!`
    manually after the request call for the same behavior.
    ([Pull Request](https://github.com/rails/rails/pull/18693))

*   Deprecated `AbstractController#skip_action_callback` in favor of individual
    skip_callback methods.
    ([Pull Request](https://github.com/rails/rails/pull/19060))

*   Deprecated `:nothing` option for `render` method.
    ([Pull Request](https://github.com/rails/rails/pull/20336))

*   Deprecated passing first parameter as `Hash` and default status code for
    `head` method.
    ([Pull Request](https://github.com/rails/rails/pull/20407))

*   Deprecated using strings or symbols for middleware class names. Use class
    names instead.
    ([commit](https://github.com/rails/rails/commit/83b767ce))

*   Deprecated accessing mime types via constants (eg. `Mime::HTML`). Use the
    subscript operator with a symbol instead (eg. `Mime[:html]`).
    ([Pull Request](https://github.com/rails/rails/pull/21869))

*   Deprecated `redirect_to :back` in favor of `redirect_back`, which accepts a
    required `fallback_location` argument, thus eliminating the possibility of a
    `RedirectBackError`.
    ([Pull Request](https://github.com/rails/rails/pull/22506))

### Notable changes

*   Added `ActionController::Renderer` to render arbitrary templates
    outside controller actions.
    ([Pull Request](https://github.com/rails/rails/pull/18546))

*   Migrating to keyword arguments syntax in `ActionController::TestCase` and
    `ActionDispatch::Integration` HTTP request methods.
    ([Pull Request](https://github.com/rails/rails/pull/18323))

*   Added `http_cache_forever` to Action Controller, so we can cache a response
    that never gets expired.
    ([Pull Request](https://github.com/rails/rails/pull/18394))

*   Provide friendlier access to request variants.
    ([Pull Request](https://github.com/rails/rails/pull/18939))

*   For actions with no corresponding templates, render `head :no_content`
    instead of raising an error.
    ([Pull Request](https://github.com/rails/rails/pull/19377))

*   Added the ability to override default form builder for a controller.
    ([Pull Request](https://github.com/rails/rails/pull/19736))

*   Added support for API only apps.
    `ActionController::API` is added as a replacement of
    `ActionController::Base` for this kind of applications.
    ([Pull Request](https://github.com/rails/rails/pull/19832))

*   Make `ActionController::Parameters` no longer inherits from
    `HashWithIndifferentAccess`.
    ([Pull Request](https://github.com/rails/rails/pull/20868))

*   Make it easier to opt in to `config.force_ssl` and `config.ssl_options` by
    making them less dangerous to try and easier to disable.
    ([Pull Request](https://github.com/rails/rails/pull/21520))

*   Added the ability of returning arbitrary headers to `ActionDispatch::Static`.
    ([Pull Request](https://github.com/rails/rails/pull/19135))

*   Changed the `protect_from_forgery` prepend default to `false`.
    ([commit](https://github.com/rails/rails/commit/39794037817703575c35a75f1961b01b83791191))

*   `ActionController::TestCase` will be moved to it's own gem in Rails 5.1. Use
    `ActionDispatch::IntegrationTest` instead.
    ([commit](https://github.com/rails/rails/commit/4414c5d1795e815b102571425974a8b1d46d932d))

Action View
-------------

Please refer to the [Changelog][action-view] for detailed changes.

### Removals

*   Removed deprecated `AbstractController::Base::parent_prefixes`.
    ([commit](https://github.com/rails/rails/commit/34bcbcf35701ca44be559ff391535c0dd865c333))

*   Removed `ActionView::Helpers::RecordTagHelper`, this functionality
    has been extracted to the
    [record_tag_helper](https://github.com/rails/record_tag_helper) gem.
    ([Pull Request](https://github.com/rails/rails/pull/18411))

*   Removed `:rescue_format` option for `translate` helper since it's no longer
    supported by I18n.
    ([Pull Request](https://github.com/rails/rails/pull/20019))

### Notable Changes

*   Changed the default template handler from `ERB` to `Raw`.
    ([commit](https://github.com/rails/rails/commit/4be859f0fdf7b3059a28d03c279f03f5938efc80))

*   Collection rendering automatically caches and fetches multiple partials.
    ([Pull Request](https://github.com/rails/rails/pull/18948))

*   Allow defining explicit collection caching using a `# Template Collection: ...`
    directive inside templates.
    ([Pull Request](https://github.com/rails/rails/pull/20781))

*   Add wildcard matching to explicit dependencies.
    ([Pull Request](https://github.com/rails/rails/pull/20904))

*   Make `disable_with` the default behavior for submit tags. Disables the
    button on submit to prevent double submits.
    ([Pull Request](https://github.com/rails/rails/pull/21135))


Action Mailer
-------------

Please refer to the [Changelog][action-mailer] for detailed changes.

### Removals

*   Removed deprecated `*_path` helpers in email views.
    ([commit](https://github.com/rails/rails/commit/d282125a18c1697a9b5bb775628a2db239142ac7))

*   Removed deprecated `deliver` and `deliver!` methods.
    ([commit](https://github.com/rails/rails/commit/755dcd0691f74079c24196135f89b917062b0715))

### Notable changes

*   Template lookup now respects default locale and I18n fallbacks.
    ([commit](https://github.com/rails/rails/commit/ecb1981b))

*   Added `_mailer` suffix to mailers created via generator, following the same
    naming convention used in controllers and jobs.
    ([Pull Request](https://github.com/rails/rails/pull/18074))

*   Added `assert_enqueued_emails` and `assert_no_enqueued_emails`.
    ([Pull Request](https://github.com/rails/rails/pull/18403))

*   Added `config.action_mailer.deliver_later_queue_name` configuration to set
    the mailer queue name.
    ([Pull Request](https://github.com/rails/rails/pull/18587))


Active Record
-------------

Please refer to the [Changelog][active-record] for detailed changes.

### Removals

### Deprecations

*   Deprecated returning `false` as a way to halt Active Record callback
    chains. The recommended way is to
    `throw(:abort)`. ([Pull Request](https://github.com/rails/rails/pull/17227))

*   Synchronize behavior of `#tables`.
    ([Pull Request](https://github.com/rails/rails/pull/21601))

*   Deprecated `connection.tables` on the SQLite3 and MySQL adapters.

*   Deprecated passing arguments to `#tables` - the `#tables` method of some
    adapters (mysql2, sqlite3) would return both tables and views while others
    (postgresql) just return tables. To make their behavior consistent,
    `#tables` will return only tables in the future.

*   Deprecated `table_exists?` - The `#table_exists?` method would check both
    tables and views. To make their behavior consistent with `#tables`,
    `#table_exists?` will check only tables in the future.

### Notable changes

*   Added a `foreign_key` option to `references` while creating the table.
    ([commit](https://github.com/rails/rails/commit/99a6f9e60ea55924b44f894a16f8de0162cf2702))

*   New attributes
    API. ([commit](https://github.com/rails/rails/commit/8c752c7ac739d5a86d4136ab1e9d0142c4041e58))

*   Added `:enum_prefix`/`:enum_suffix` option to `enum`
    definition. ([Pull Request](https://github.com/rails/rails/pull/19813))

*   Added `#cache_key` to `ActiveRecord::Relation`.
    ([Pull Request](https://github.com/rails/rails/pull/20884))

*   Added `ActiveRecord::Relation#outer_joins`.
    ([Pull Request](https://github.com/rails/rails/pull/12071))

*   Require `belongs_to` by default.
    ([Pull Request](https://github.com/rails/rails/pull/18937)) - Deprecate
    `required` option in favor of `optional` for `belongs_to`


Active Model
------------

Please refer to the [Changelog][active-model] for detailed changes.

### Removals

*   Removed deprecated `ActiveModel::Dirty#reset_#{attribute}` and
    `ActiveModel::Dirty#reset_changes`.
    ([Pull Request](https://github.com/rails/rails/commit/37175a24bd508e2983247ec5d011d57df836c743))

*   Removed XML serialization. This feature has been extracted into the
    [activemodel-serializers-xml](https://github.com/rails/activemodel-serializers-xml) gem.
    ([Pull Request](https://github.com/rails/rails/pull/21161))

### Deprecations

*   Deprecated returning `false` as a way to halt Active Model and
    `ActiveModel::Validations` callback chains. The recommended way is to
    `throw(:abort)`. ([Pull Request](https://github.com/rails/rails/pull/17227))

*   Deprecated `ActiveModel::Errors#get`, `ActiveModel::Errors#set` and
    `ActiveModel::Errors#[]=` methods that have inconsistent behavior.
    ([Pull Request](https://github.com/rails/rails/pull/18634))

*   Deprecated the `:tokenizer` option for `validates_length_of`, in favor of
    plain Ruby.
    ([Pull Request](https://github.com/rails/rails/pull/19585))

*   Deprecated `ActiveModel::Errors#add_on_empty` and `ActiveModel::Errors#add_on_blank`
    with no replacement.
    ([Pull Request](https://github.com/rails/rails/pull/18996))

### Notable changes

*   Added `ActiveModel::Errors#details` to determine what validator has failed.
    ([Pull Request](https://github.com/rails/rails/pull/18322))

*   Extracted `ActiveRecord::AttributeAssignment` to `ActiveModel::AttributeAssignment`
    allowing to use it for any object as an includable module.
    ([Pull Request](https://github.com/rails/rails/pull/10776))

*   Added `ActiveModel::Dirty#[attr_name]_previously_changed?` and
    `ActiveModel::Dirty#[attr_name]_previous_change` to improve access
    to recorded changes after the model has been saved.
    ([Pull Request](https://github.com/rails/rails/pull/19847))

*   Validate multiple contexts on `valid?` and `invalid?` at once.
    ([Pull Request](https://github.com/rails/rails/pull/21069))


Active Job
-----------

Please refer to the [Changelog][active-job] for detailed changes.

### Notable changes

*   `ActiveJob::Base.deserialize` delegates to the job class. this allows jobs
    to attach arbitrary metadata when they get serialized and read it back when
    they get performed.
    ([Pull Request](https://github.com/rails/rails/pull/18260))

*   A generated job now inherits from `app/jobs/application_job.rb` by default.
    ([Pull Request](https://github.com/rails/rails/pull/19034))

*   Allow `DelayedJob`, `Sidekiq`, `qu`, and `que` to report the job id back to
    `ActiveJob::Base` as `provider_job_id`.
    ([Pull Request](https://github.com/rails/rails/pull/20064),
     [Pull Request](https://github.com/rails/rails/pull/20056))

*   Implement a simple `AsyncJob` processor and associated `AsyncAdapter` that
    queue jobs to a `concurrent-ruby` thread pool.
    ([Pull Request](https://github.com/rails/rails/pull/21257))


Active Support
--------------

Please refer to the [Changelog][active-support] for detailed changes.

### Removals

*   Removed deprecated `ActiveSupport::JSON::Encoding::CircularReferenceError`.
    ([commit](https://github.com/rails/rails/commit/d6e06ea8275cdc3f126f926ed9b5349fde374b10))

*   Removed deprecated methods `ActiveSupport::JSON::Encoding.encode_big_decimal_as_string=`
    and `ActiveSupport::JSON::Encoding.encode_big_decimal_as_string`.
    ([commit](https://github.com/rails/rails/commit/c8019c0611791b2716c6bed48ef8dcb177b7869c))

*   Removed deprecated `ActiveSupport::SafeBuffer#prepend`.
    ([commit](https://github.com/rails/rails/commit/e1c8b9f688c56aaedac9466a4343df955b4a67ec))

*   Removed deprecated methods from `Kernel`. `silence_stderr`, `silence_stream`,
    `capture` and `quietly`.
    ([commit](https://github.com/rails/rails/commit/481e49c64f790e46f4aff3ed539ed227d2eb46cb))

*   Removed deprecated `active_support/core_ext/big_decimal/yaml_conversions`
    file.
    ([commit](https://github.com/rails/rails/commit/98ea19925d6db642731741c3b91bd085fac92241))

*   Removed deprecated methods `ActiveSupport::Cache::Store.instrument` and
    `ActiveSupport::Cache::Store.instrument=`.
    ([commit](https://github.com/rails/rails/commit/a3ce6ca30ed0e77496c63781af596b149687b6d7))

*   Removed deprecated `Class#superclass_delegating_accessor`.
    Use `Class#class_attribute` instead.
    ([Pull Request](https://github.com/rails/rails/pull/16938))

*   Removed deprecated `ThreadSafe::Cache`. Use `Concurrent::Map` instead.
    ([Pull Request](https://github.com/rails/rails/pull/16938))

### Deprecations

*   Deprecated `MissingSourceFile` in favor of `LoadError`.
    ([commit](https://github.com/rails/rails/commit/734d97d2))

*   Deprecated `alias_method_chain` in favour of `Module#prepend` introduced in
    Ruby 2.0.
    ([Pull Request](https://github.com/rails/rails/pull/19434))

*   Deprecated `ActiveSupport::Concurrency::Latch` in favor of
    `Concurrent::CountDownLatch` from concurrent-ruby.
    ([Pull Request](https://github.com/rails/rails/pull/20866))

*   Deprecated `:prefix` option of `number_to_human_size` with no replacement.
    ([Pull Request](https://github.com/rails/rails/pull/21191))

*   Deprecated `Module#qualified_const_` in favour of the builtin
    `Module#const_` methods.
    ([Pull Request](https://github.com/rails/rails/pull/17845))

*   Deprecated passing string to define callback.
    ([Pull Request](https://github.com/rails/rails/pull/22598))

*   Deprecated `ActiveSupport::Cache::Store#namespaced_key`,
    `ActiveSupport::Cache::MemCachedStore#escape_key`, and
    `ActiveSupport::Cache::FileStore#key_file_path`.
    Use `normalize_key` instead.

    Deprecated `ActiveSupport::Cache::LocaleCache#set_cache_value` in favor of `write_cache_value`.
    ([Pull Request](https://github.com/rails/rails/pull/22215))

### Notable changes

*   Added `#verified` and `#valid_message?` methods to
    `ActiveSupport::MessageVerifier`.
    ([Pull Request](https://github.com/rails/rails/pull/17727))

*   Changed the way in which callback chains can be halted. The preferred method
    to halt a callback chain from now on is to explicitly `throw(:abort)`.
    ([Pull Request](https://github.com/rails/rails/pull/17227))

*   New config option
    `config.active_support.halt_callback_chains_on_return_false` to specify
    whether ActiveRecord, ActiveModel and ActiveModel::Validations callback
    chains can be halted by returning `false` in a 'before' callback.
    ([Pull Request](https://github.com/rails/rails/pull/17227))

*   Changed the default test order from `:sorted` to `:random`.
    ([commit](https://github.com/rails/rails/commit/5f777e4b5ee2e3e8e6fd0e2a208ec2a4d25a960d))

*   Added `#on_weekend?`, `#next_weekday`, `#prev_weekday` methods to `Date`,
    `Time`, and `DateTime`.
    ([Pull Request](https://github.com/rails/rails/pull/18335))

*   Added `same_time` option to `#next_week` and `#prev_week` for `Date`, `Time`,
    and `DateTime`.
    ([Pull Request](https://github.com/rails/rails/pull/18335))

*   Added `#prev_day` and `#next_day` counterparts to `#yesterday` and
    `#tomorrow` for `Date`, `Time`, and `DateTime`.
    ([Pull Request](httpshttps://github.com/rails/rails/pull/18335))

*   Added `SecureRandom.base58` for generation of random base58 strings.
    ([commit](https://github.com/rails/rails/commit/b1093977110f18ae0cafe56c3d99fc22a7d54d1b))

*   Added `file_fixture` to `ActiveSupport::TestCase`.
    It provides a simple mechanism to access sample files in your test cases.
    ([Pull Request](https://github.com/rails/rails/pull/18658))

*   Added `#without` on `Enumerable` and `Array` to return a copy of an
    enumerable without the specified elements.
    ([Pull Request](https://github.com/rails/rails/pull/19157))

*   Added `ActiveSupport::ArrayInquirer` and `Array#inquiry`.
    ([Pull Request](https://github.com/rails/rails/pull/18939))

*   Added `ActiveSupport::TimeZone#strptime` to allow parsing times as if
    from a given timezone.
    ([commit](https://github.com/rails/rails/commit/a5e507fa0b8180c3d97458a9b86c195e9857d8f6))

*   Added `Integer#positive?` and `Integer#negative?` query methods
    in the vein of `Fixnum#zero?`.
    ([commit](https://github.com/rails/rails/commit/e54277a45da3c86fecdfa930663d7692fd083daa))

*   Added a bang version to `ActiveSupport::OrderedOptions` get methods which will raise
    an `KeyError` if the value is `.blank?`.
    ([Pull Request](https://github.com/rails/rails/pull/20208))

*   Added `Time.days_in_year` to return the number of days in the given year, or the
    current year if no argument is provided.
    ([commit](https://github.com/rails/rails/commit/2f4f4d2cf1e4c5a442459fc250daf66186d110fa))

*   Added an evented file watcher to asynchronously detect changes in the
    application source code, routes, locales, etc.
    ([Pull Request](https://github.com/rails/rails/pull/22254))

*   Add thread_m/cattr_accessor/reader/writer suite of methods for declaring
    class and module variables that live per-thread.
    ([Pull Request](https://github.com/rails/rails/pull/22630))


Credits
-------

See the
[full list of contributors to Rails](http://contributors.rubyonrails.org/) for
the many people who spent many hours making Rails, the stable and robust
framework it is. Kudos to all of them.

[railties]:       https://github.com/rails/rails/blob/5-0-stable/railties/CHANGELOG.md
[action-pack]:    https://github.com/rails/rails/blob/5-0-stable/actionpack/CHANGELOG.md
[action-view]:    https://github.com/rails/rails/blob/5-0-stable/actionview/CHANGELOG.md
[action-mailer]:  https://github.com/rails/rails/blob/5-0-stable/actionmailer/CHANGELOG.md
[active-record]:  https://github.com/rails/rails/blob/5-0-stable/activerecord/CHANGELOG.md
[active-model]:   https://github.com/rails/rails/blob/5-0-stable/activemodel/CHANGELOG.md
[active-support]: https://github.com/rails/rails/blob/5-0-stable/activesupport/CHANGELOG.md
[active-job]:     https://github.com/rails/rails/blob/5-0-stable/activejob/CHANGELOG.md