<template>
<div class="modal" :id="id" tabindex="-1" role="dialog" :aria-labelledby="id+'Label'" aria-hidden="true">
  <div class="modal-dialog modal-sm" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" :id="id+'Label'">{{header}}</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
          {{message}}
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button
            v-if="bug_report_email"
            @click="send_bug_report"
            type="button"
            class="btn btn-primary">Send Bug Report
        </button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
    props: [
        'modal_id',
        'message',
        'header',
        'bug_report_email',
        'bug_report_subject',
        'bug_report_message'
    ],

    data: function() {
        return {
            id: 'AlertModal',
        }
    },

    methods: {
        send_bug_report: function() {
            window.location.href = `mailto:${this.bug_report_email}?subject=${this.bug_report_subject}&body=${this.bug_report_message}`;
        }
    }
}
</script>
