<template>

  <DocsPageTemplate>

    <DocsPageSection title="Overview" anchor="#overview">
      <p>
        Snackbars are short and affirmative messages that momentarily grab the user’s attention to convey non-critical information. They are transient and do not persist on the page.
      </p>
    </DocsPageSection>

    <DocsPageSection title="Usage" anchor="#usage">
      <p>
        Snackbars typically appear following an action taken by the user, and the contents of the snackbar should inform the user something about the results of an operation starting or completing successfully.
      </p>
      <p>Snackbars should be located 24px from the bottom-left corner of the screen.</p>
      <p>Only one snackbar should be visible at a time. If multiple snackbars need to appear, have them appear sequentially, replacing the previous snackbar.</p>
      <p>
        Avoid using snackbars for critical information. It may be difficult for users with low dexterity or vision to access it. Consider using an alert banner or modal instead.
      </p>
      <p>
        Snackbars can occasionally be used for other purposes. Some atypical use-cases include alerts for being signed out due to inactivity, or prompting the user to move on after completing a resource.
      </p>
    </DocsPageSection>

    <DocsPageSection title="Inline buttons" anchor="#inline-buttons">
      <p>
        Snackbars may occasionally include a button so the user can take a follow-up, non-critical action. Common examples are 'undo' and 'retry'. Note that some users will never have the opportunity to click this button.
      </p>
      <p>
        Here is an example of a snackbar with an inline button:
      </p>
      <img src="path/to/your/snackbar-with-button.png" alt="Snackbar with button" />
    </DocsPageSection>

    <DocsPageSection title="Text content" anchor="#text-content">
      <p>
        Snackbar messages should be concisely written sentence fragments. Examples include:
      </p>
      <ul>
        <li>Profile updated</li>
        <li>Changes saved</li>
        <li>Resource added</li>
      </ul>
      <p>Avoid including user-inputted text such as the name of a resource or lesson because we have less control over the length of this text.</p>
      <p>
        Example of a basic snackbar message:
      </p>
      <img src="path/to/your/snackbar-message-example.png" alt="Basic Snackbar Example" />
    </DocsPageSection>

    <DocsPageSection title="Snackbar Variations" anchor="#snackbar-variations">
      <h2>Snackbar Variations</h2>
      <p>Here are different variations of snackbars you can implement:</p>

      <h3>Basic Snackbar</h3>
      <p>
        A simple snackbar with a message only, no action button. The text should not be very long as it is designed to convey brief, non-critical information.
      </p>
      <img src="./snackbars/basic.jpg" alt="Basic Snackbar" />

      <h3>Snackbar with Action Button</h3>
      <p>
        This variation includes an action button, like 'Undo' or 'Retry'. The action button is not highlighted with a background, and it is styled with a different color (e.g., purple) to distinguish it from the normal text.
      </p>
      <img src="./snackbars/withaction.jpg" alt="Snackbar with Action" />
      <ul>
        <li>Button Text: Customizable (e.g., "Undo", "Retry")</li>
        <li>Button color: Green (e.g., #81c784 for focused state)</li>
        <li>Timeout: 4 seconds</li>
      </ul>

      <h3>Focused Snackbar</h3>
      <p>
        This snackbar variation highlights the focused state, typically used for active tasks or high-priority alerts. The focused state does not change the background color, but emphasizes the snackbar with a subtle visual effect.
      </p>
      <img src="./snackbars/focused1.jpg" alt="Focused Snackbar" />
      <ul>
        <li>Focused state color: #dc8aff</li>
        <li>Focused state: Applies a slight visual focus effect, such as a border highlight or text changes</li>
      </ul>

    </DocsPageSection>

    <DocsPageSection title="General Specifications" anchor="#general-specifications">
      <h3>General Snackbar Specifications</h3>
      <ul>
        <li>Background color: $k-grey-900</li>
        <li>Text: 14px white and bolded</li>
        <li>Height: 48px</li>
        <li>Min width: 344px</li>
        <li>Max width: 512px</li>
        <li>Timeout: 4 seconds</li>
        <li>Box shadow: 0 2px 8px 0 rgba(0, 0, 0, 0.25)</li>
        <li>Corner radius: 4px</li>
      </ul>
    </DocsPageSection>

    <DocsPageSection title="Component Properties" anchor="#component-properties">
      <h3>Snackbar Component Properties</h3>
      <p>The following properties are passed to the snackbar component:</p>
      <ul>
        <li><strong>message</strong>: The content to display in the snackbar (e.g., "Profile updated").</li>
        <li><strong>actionText</strong>: Optional text for an action button (e.g., "Undo").</li>
        <li><strong>actionCallback</strong>: Optional callback function for the action button.</li>
        <li><strong>color</strong>: Background color of the snackbar. Default: `$k-grey-900`.</li>
        <li><strong>focused</strong>: Boolean flag to indicate whether the snackbar is in focus (e.g., for high-priority or active messages). Default: `false`.</li>
        <li><strong>timeout</strong>: Duration in milliseconds before the snackbar disappears. Default: `4000` (4 seconds).</li>
      </ul>
    </DocsPageSection>

  </DocsPageTemplate>

</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
/* Add any custom styling if needed */
</style>
