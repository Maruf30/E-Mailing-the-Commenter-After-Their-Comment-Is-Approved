# E-Mailing-the-Commenter-After-Their-Comment-Is-Approved


add_action( 'comment_unapproved_to_approved', 'comment_unapproved_to_approved_example' );
  
function comment_unapproved_to_approved_example( $comment ) {
  
    $commenter_email = $comment->comment_author_email;
    $commenter_name  = $comment->comment_author;
    $post_url = get_comment_link( $comment );
    $subject = "Your comment is up!";
    $message = "Hello $commenter_name,\n\nYour comment has been approved!You can view it below:\n\n$post_url\n\nThank you for sharing your ideas with us!";
  
    wp_mail( $commenter_email, $subject, $message );
}
