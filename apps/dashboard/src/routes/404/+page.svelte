<script>
  import { goto } from '$app/navigation';

  import { appStore } from '$lib/utils/store/app';
  import PrimaryButton from '$lib/components/PrimaryButton/index.svelte';

  const src = './bg-404.png';
</script>

<div
  style={$appStore.isDark ? `background-image:url(${src})` : ''}
  class={`error bg-gray-200 bg-no-repeat bg-cover flex items-center justify-center w-screen gap-20`}
>
  <div class=" dark:text-white gap-3 w-4/5 lg:w-2/5">
    <p class="text-3xl dark:text-white font-semibold mb-5">
      Oops😕,where did the page go?
    </p>
    <p class="text-base text-gray-600 dark:text-white mb-5">
      We're sorry, but something went wrong and we can't show you the page
      you're looking for. In the meantime, here's a joke to make you laugh:<br
      />
      What do you call a fish with no eyes? Fsh!
    </p>
    <PrimaryButton
      label="Go to Home"
      className="rounded-md"
      onClick={() => goto('/')}
    />
  </div>

  <img
    src="/classroom-404.png"
    alt="classroomio_error_image"
    class="errorImg"
  />
</div>

<style>
  .error {
    height: calc(100vh - 57px);
  }

  @media (max-width: 920px) {
    .error {
      flex-direction: column-reverse;
      gap: 20px;
    }
    .errorImg {
      width: 160px;
      height: 160px;
    }
  }
</style>
