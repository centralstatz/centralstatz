```{=html}
<div class="list">
<% for (const item of items) { %>
<article class="lab-project-card" <%= metadataAttrs(item) %>>
  <a class="project-preview" href="<%- item.path %>" aria-label="Open project notebook for <%- item.title %>">
    <% if (item.image) { %>
    <img src="<%- item.image %>" alt="<%- item.preview_alt || '' %>" loading="lazy">
    <% } else { %>
    <div class="preview-placeholder" role="img" aria-label="Concept preview placeholder"><span>Preview pending</span></div>
    <% } %>
    <span class="preview-label"><%- item.visual_is_concept ? 'Concept diagram' : (item.visual_type === 'project-output' ? 'Project output' : 'Working interface') %></span>
  </a>
  <div class="project-card-body">
    <div class="project-meta">
      <span class="status-chip"><span class="status-dot" aria-hidden="true"></span><%- item.status %></span>
      <span><%- item.category %></span>
    </div>
    <h3><a href="<%- item.path %>"><%- item.title %></a></h3>
    <p class="project-summary"><%- item.description %></p>
    <div class="stage-track" aria-label="Project stage: <%- item.stage %>">
      <% const stages = ['Question', 'Concept', 'Prototype', 'Validation', 'Pilot', 'Production']; const current = stages.indexOf(item.stage); %>
      <% stages.forEach(function(stage, index) { %>
      <span class="stage-step <%= index === current ? 'is-current' : '' %> <%= index < current ? 'is-complete' : '' %>">
        <span class="stage-marker" aria-hidden="true"></span><span class="stage-name"><%- stage %></span>
      </span>
      <% }); %>
    </div>
    <div class="project-facts">
      <div><span>Central question</span><p><%- item.central_question %></p></div>
      <div><span>Current state</span><p><%- item.current_state %></p></div>
      <div><span>Latest update</span><p><%- item.latest_update %></p></div>
      <div><span>Next experiment</span><p><%- item.next_step %></p></div>
    </div>
    <% if (item.limitations) { %>
    <p class="project-caveat"><strong>Known limits:</strong> <%- item.limitations %></p>
    <% } %>
    <div class="project-card-footer">
      <p><span>Looking for</span><%- item.looking_for %></p>
      <a class="text-link" href="<%- item.path %>">Open project notebook <span aria-hidden="true">&rarr;</span></a>
    </div>
  </div>
</article>
<% } %>
</div>
```
