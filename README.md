#### Changes

Model triggering 'after_sync' after Backbone.sync gets 2xx from sync with backend.
This gives more event driven passion in view code
  
```coffeescript  
  class window.EditableUserInfoView extends Backbone.View
      ...
       
      initialize: (attributes, options) ->            
          @after_save_callback  = (options && options['after_save']) || @change_to_display_mode
          @model.bind 'change', @render
          @model.bind 'error', @show_validation_error
          @model.bind 'after_save', @after_save_callback
      ...
```
