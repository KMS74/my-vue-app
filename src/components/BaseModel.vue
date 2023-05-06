<template lang="">
  <!-- Modal trigger button -->
  <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#modalId">
    Add Student
  </button>

  <!-- Modal Body -->
  <!-- if you want to close by clicking outside the modal, delete the last endpoint:data-bs-backdrop and data-bs-keyboard -->
  <Teleport to="body">
    <div
      class="modal fade"
      id="modalId"
      tabindex="-1"
      data-bs-backdrop="static"
      data-bs-keyboard="false"
      role="dialog"
      aria-labelledby="modalTitleId"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-dialog-centered" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <slot name="header">Model Header</slot>
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-body">
            <slot name="student-form"></slot>
          </div>
          <div class="modal-footer">
            <slot name="model-buttons"></slot>
          </div>
        </div>
      </div>
    </div>
  </Teleport>
</template>
<script>
export default {}
</script>
<style lang=""></style>
