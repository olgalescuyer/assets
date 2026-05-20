Consent Manager Installation Instructions

1. Extract the contents of this zip file
2. Place the files in your website directory
3. Add the following code to your HTML page, inside the <head> tag:

<link rel="preconnect" href="https://cdn.jsdelivr.net" crossorigin>
<link rel="stylesheet" id="consent-manager-css" href="" integrity="" crossorigin="anonymous">
<script src="" integrity="" crossorigin="anonymous"></script>

<script>
window.consentManager.init({
  backdrop: {
    show: true
  },
  icon: {
    position: "bottomRight"
  },
  prompt: {
    position: "center"
  },
  consentTypes: [
    {
      id: "essential",
      label: "Essential",
      description: "<p>These cookies are necessary for the website to function properly and cannot be switched off. They help with things like logging in and setting your privacy preferences.</p>",
      required: true,
      onAccept: function() {
        console.log('Add logic for the required Essential consent type here');
      }
    },
    {
      id: "analytics",
      label: "Analytics",
      description: "<p>These cookies help us improve the site by tracking which pages are most popular and how visitors move around the site.</p>",
      required: true,
      gtag: "analytics_storage",
      onAccept: function() {
        console.log('Add logic for the required Analytics consent type here');
      }
    },
    {
      id: "marketing",
      label: "Marketing",
      description: "<p>These cookies are used by us and our advertising partners to show you relevant ads on this site and elsewhere, and to measure how those campaigns perform.</p>",
      required: true,
      gtag: [
        "ad_storage",
        "ad_user_data",
        "ad_personalization"
      ],
      onAccept: function() {
        console.log('Add logic for the required Marketing consent type here');
      }
    }
  ],
  text: {
    prompt: {
      description: "<p>We use cookies on our site to enhance your user experience, provide personalized content, and analyze our traffic.</p>",
      acceptAllButtonText: "Accept all",
      acceptAllButtonAccessibleLabel: "Accept all cookies",
      rejectNonEssentialButtonText: "Reject non-essential",
      rejectNonEssentialButtonAccessibleLabel: "Reject all non-essential cookies",
      preferencesButtonText: "Preferences",
      preferencesButtonAccessibleLabel: "Toggle preferences"
    },
    preferences: {
      title: "Customize your cookie preferences",
      description: "<p>We respect your right to privacy. You can choose not to allow some types of cookies. Your cookie preferences will apply across our website.</p>",
      saveButtonText: "Save and close",
      saveButtonAccessibleLabel: "Save your cookie preferences"
    }
  }
});
</script>
